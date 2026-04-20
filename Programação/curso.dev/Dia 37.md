Com a finalização da primeira milestone no [[Dia 35]]  e definindo as issues da próxima milestone no Dia 36, que tratará de autenticação e autorização, no dia 37, criamos o frontend do `/status`, a primeira página pública da aplicação e que visa exibir o status dos serviços. 

A ideia é consumir o endpoint `/api/v1/status` em uma página pública disponibilizada em `/status` e exibir as informações obtidas na interface.

Ao dirigir um carro não precisamos saber como o motor funciona ou o que cada uma de suas peças faz, só precisamos fornecer ao carro os inputs necessários, como a pressão no acelerador ou a posição do volante, a base do [[Dia 3#React|React]] é a componentização,  a ideia é abstrair, "abrir o capô", criar o funcionamento interno de cada componente e  unir componentes mais simples em componentes mais complexos.

Podemos criar a página pública de status, criando um arquivo  no caminho `src/app/status/page.tsx`  da seguinte maneira:

```jsx
export default function StatusPage(){
	return (
	<>
	  <h1>Status</h1>
	</>
	)
}
```

Cada componente `React` tem três aspectos: Visual, Funcionalidade e Memória. Com esse primeiro componente, já atingimos o aspecto visual, o próximo passo é então adicionar a funcionalidade fazendo o `Data fetching` do endpoint ``api/v1/status``, de forma simples, isso pode ser feito criando um novo componente da seguinte maneira:

```jsx
async function fetchStatus() {
  const response = await fetch('http://localhost:3000/api/v1/status');
  return response.json();
}

export async function UpdatedAt() {
  const data = await fetchStatus();
  const updatedAt = new Date(data.updated_at).toLocaleString('pt-BR');

  return <p>{updatedAt}</p>;
}

export default function StatusPage() {
  return (
    <>
      <h1>Status</h1>
      <UpdatedAt />
    </>
  );
}
```

Nesse formato, no entanto, perdemos muita eficiência, sobretudo a medida que nossos componentes ficam mais complexos, já que o componente só poder ser renderizado quando a `promisse` do `UpdatedAt` for resolvida, além disso, a comunidade do React, tem incentivado cada vez mais a adoção dos chamados `fetchers` ao invés de controlar manualmente a requisição, já que estes garantem um controle e eficiência muito maior no controle das requisições e funcionalidades como evitar a duplicação de requests ou mesmo o caching. Dois exemplos de `fetcher` são o `SWR` (Menos famoso, mas criado pela própria Vercel) e o `React-Query` (Queridinho da comunidade).

# ``SWR``
Para usar o `SWR` instalamos o pacote através do comando:

```bash
npm i swr
```

Depois disso, fazemos as requisições na nossa API através do hook `useSWR`, nossa página de status ficaria então:

```jsx
'use client';

import useSWR from 'swr';
  
async function fetchStatus() {
  const response = await fetch('http://localhost:3000/api/v1/status');
  
  return response.json();
}

export function UpdatedAt() {
  const { data, isLoading } = useSWR('status', fetchStatus);
  
  if (isLoading) {
    return <p>Carregando...</p>;
  }
  
  const updatedAt = new Date(data.updated_at).toLocaleString('pt-BR');
  
  return <p>{updatedAt}</p>;
}

export default function StatusPage() {
  return (
    <>
      <h1>Status</h1>
      <UpdatedAt />
    </>
  );
}
```

Agora, enquanto carrega a requisição, o objeto retornado pelo `useSWR`  têm uma propriedade `isLoading` com o valor `true` e usamos isso para retornar um elemento html `<p>Carregando...</p>` enquanto a requisição não é finalizada, quando a request termina, esse valor atualiza para `false` e uma outra propriedade `data` do objeto que era `undefined` enquanto a requisição não era resolvida, agora detêm o valor retornado pela função `fetchStatus`.  

Além disso, a string `"status"`, passada para o `useSWR` é a chamada `key` da requisição e faz parte de um sistema de deduplicação de requests, isto é, o `SWR` faz uma espécie de cache da requisição e caso uma request seja feita para um mesmo `url` e usando a mesma `key` dentro de um período de tempo predefinido, ao invés de repetir a requisição, o `SWR` simplesmente retorna o valor salvo em cache, evitando múltiplas requests iguais e acelerando o período de carregamento.

O terceiro argumento que podemos passar para o `useSWR` é um objeto de configurações para o seu funcionamento, por exemplo, podemos passar um objeto com a propriedade `refreshInterval` definida com `2000` o que fará com que a cada 2 segundos (2000 milissegundos) a request seja repetida e atualize automaticamente as informações na interface, um outro exemplo,  é passar um objeto com a propriedade `dedupingInterval` com o valor ``2000``, o que fará com que o sistema de deduplicação de request tenha como tempo predefinido o valor de 2 segundos.

OBS: O `useSWR` é um hook react e contém algumas funcionalidade que só são permitidas em client components, por isso, sempre que o usarmos, deve estar explícito no topo do arquivo o valor ``"use client";``.

# `React-query`
Uma alternativa mais completa, mas também mais complexa, ao `SWR` é o `React-query`, o pacote mais conhecido com essa finalidade, para instalá-lo usamos o comando:

```bash
npm i @tanstack/react-query
```

Diferente do `SWR`, aqui nós precisamos realizar uma configuração inicial, envolvendo a nossa aplicação no `Provider` do `react-query`, podemos fazer isso de forma escalável, criando um componente chamado `Providers` com o seguinte formato:

```tsx
'use client';

import { QueryClient, QueryClientProvider } from '@tanstack/react-query';
import { useState } from 'react';

export default function Providers({ children }: { children: React.ReactNode }) {
  const [queryClient] = useState(() => new QueryClient());

  return (
    <QueryClientProvider client={queryClient}>{children}</QueryClientProvider>
  );
}
```

E então no `layout.tsx` envolvemos o restante da aplicação com o componente criado:

```tsx
import Providers from './providers';

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {

  return (
    <html lang="pt-BR">
      <body>
        <Providers>{children}</Providers>
      </body>
    </html>
  );
}
```

Depois disso, no componente em que queremos fazer o fetch usamos o hook `useQuery` da seguinte maneira:

```tsx
'use client';

import { useQuery } from '@tanstack/react-query';

async function fetchStatus() {
  const response = await fetch('http://localhost:3000/api/v1/status');
  
  return response.json();
}

export function UpdatedAt() {
  const { data, isLoading } = useQuery({
    queryKey: ['status'],
    queryFn: fetchStatus,
    refetchInterval: 2000,
    staleTime: 2000,
  });

  if (isLoading) {
    return <p>Carregando...</p>;
  }
  
  const updatedAt = new Date(data.updated_at).toLocaleString('pt-BR');

  return <p>{updatedAt}</p>;
}

export default function StatusPage() {
  return (
    <>
      <h1>Status</h1>
      <UpdatedAt />
    </>
  );
}
```

Esse componente tem comportamento idêntico ao componente exemplificado anteriormente para o `SWR`, aqui, as configurações da request são todas passadas dentro de um objeto, até mesmo a função (`queryFn`) e a nossa `key` (`querykey`), a config `refetchInterval` equivale ao `refreshInterval`  e a config `staleTime` equivale ao `dedupingInterval`, ambas do `SWR`.

Além do `isLoading`, o `useQuery` também retorna as props `isPending`, `isError`, `isSuccess` e `isFetching` além de `data` e `error`.

A primeira versão da nossa página de status fica então:

```tsx
'use client';
import { useQuery } from '@tanstack/react-query';

async function fetchStatus() {
  const response = await fetch('http://localhost:3000/api/v1/status');
  
  return response.json();
}

  

export function UpdatedAt() {
  const { data, isLoading } = useQuery({
    queryKey: ['status'],
    queryFn: fetchStatus,
    refetchInterval: 2000,
    staleTime: 2000,
  });

  if (isLoading) {
    return <p>Carregando...</p>;
  }

  const updatedAt = new Date(data.updated_at).toLocaleString('pt-BR');

  return <p>Atualizado em: {updatedAt}</p>;
}

  

export function DatabaseStatus() {
  const { data, isLoading } = useQuery({
    queryKey: ['status'],
    queryFn: fetchStatus,
    refetchInterval: 2000,
    staleTime: 2000,
  });

  if (isLoading) {
    return <p>Carregando...</p>;
  }

  const version = data.dependencies.database.version;
  const maxConnections = data.dependencies.database.max_connections;
  const openedConnections = data.dependencies.database.opened_connections;

  return (
    <>
      <p>Versão: {version}</p>
      <p>Máximo de conexões: {maxConnections}</p>
      <p>Conexões abertas: {openedConnections}</p>
    </>
  );
}

export default function StatusPage() {
  return (
    <>
      <h1>Status</h1>
      <UpdatedAt />
      <h2>Banco de dados</h2>
      <DatabaseStatus />
    </>
  );
}
```