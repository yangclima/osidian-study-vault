O sistema de tipos presente no TS pode ser dito como **gradual** e **opcional**, gradual por que pode ser implementado pouco a pouco no eu código e opcional por que pode ser desligado ou ignorado quando quisermos, a chave para isso é o tipo `any`.

É comum que ao começarmos a usar o TS sejamos tentados a frequentemente usar `any` ou a assertion `as any` nas nossas tipagens, seja por que não entendemos um erro, por que queremos resolvê-lo rapidamente ou mesmo por que achamos que o type checker está errado.

Apesar de isso ser aceitável em alguns casos, é essencial ter em mente alguns extremamente relevantes desvantagens de usar esses artifícios:

# Não há segurança de tipos com `any`
Mesmo que uma variável seja tipada corretamente, se usarmos `as any` ao atribuir um valor a ela o type checker acreditará que ela segue a tipagem te indicando em outras partes do código que você pode fazer operações com ela que não são de fato válidas, sendo fonte de diversos erros em runtime ou mesmo de lógica:

```ts
let age: number;
age = '12' as any;

age += 1; // Sem Erro, mas `age` em runtime será '121'
```

# User `any` te faz quebrar contratos
Quando escrevemos uma função, basicamente estamos estabelecendo um contrato: "Se você me entregar um argumento que segue uma série de constraints eu te devolverei um determinado tipo de saída", o ponto é que se uma variável é tipada como `any` o type checker não consegue garantir o seu tipo e por isso não aponta erros quando tentamos passar essa variável como argumento de uma função que pede outro tipo de argumento.

```ts
const calculateAge = (birthDate: Date): number => { /* ... */ };
const birthDate: any = "1990-01-01";

const age = calculateAge(birthDate); // OK
```

Isso é muito problemático por que o JS por baixo dos panos tenta constantemente converter implicitamente as variáveis.

# Não existem serviços de linguagem para tipos `any`
Quando usamos o TS a nossa IDE usa seus sistema de tipos para criar sugestões úteis de código, autocomplete e muito mais, entretanto, quando usamos `any` para tipar as variáveis nós tiramos essa possibilidade, os serviços de linguagem não funcionam e nossa produtividade decai e também a de todo o restante do time.

# `any` mascara bugs de refatoração
Quando escrevemos código com tipos específicos ao invés de `any` esse tipos servem como um guia ao refatorar nosso código e evitam muitos erros de lógica, quando usamos `any`, entretanto, perdemos essa vantagem e muitos bugs serão mascarados.

# `any` esconde o seu design de tipos
O design de tipos é essencial para escrever um código limpo, legível e correto, entretanto, quando usamos `any` nós deixamos esse design implícito tornando difícil validá-lo, avaliá-lo ou mesmo compreendê-lo.

# `any` te faz perder a confiança no sistema de tipos
Sempre que usamos tipos corretamente e ele nos aponta um bug ou oferece um autocomplete ganhamos mais confiança nesse sistema, entretanto, sempre que usamos `any` e eventualmente o sistema falha, mascara um bug, permite um erro em runtime, entre outro, perdemos um pouco a confiança nele. 

Além disso, TypeScript cheio de `any` pode ser mais difícil de trabalhar que o JS puro, perdendo a grande maioria das suas vantagens e se tornando mais um fardo para a sua stack.

