O dia 29 trouxe algumas ferramentas importantes para a implementação do CI em nossos projetos pessoais.
# Implementando Continuous Integration
A integração contínua precisa ser implementada em etapas: 

1. Estabilizar o ambiente local
2. Estabilizar o testes locais
3. Implementar o CI

O caso é: A implementação do CI depende do funcionamento independente do ambiente local, já que os testes dependem desse funcionamento e o CI depende da execução correta desses testes para conferir o funcionamento do sistema antes de cada commit ser aprovado.
## Estabilizando o ambiente local
O primeiro passo, como vimos, é a estabilização do ambiente local, como sabemos, a execução do ambiente local precisa passar por etapas: 
$$
\text{subir os serviços} \rightarrow \text{rodar as migrations} \rightarrow \text{rodar o servidor de desenvolvimento}
$$
O problema começa no funcionamento da primeira etapa, assim que o container [[Dia 17#Docker|docker]] sobe, mesmo antes do banco de dados estar pronto o processo emite um exit code de sucesso, liberando a execução do próximo processo, o grande problema é: o próximo processo são as migrations que não serão executadas com sucesso a menos que o branco de dados esteja pronto, assim, a solução é criar um passo intermediário que roda um script que garante que o banco de dados esteja pronto antes de liberar a execução das migrations:
### Testando a disponibilidade do banco de dados:
Para saber se o banco de dados está funcionando, podemos utilizar um comando docker, executado no container específico do Postgres: 
```bash
docker exec <containerName> pg-isready --host <host> 
```
A especificação do host não é obrigatória, porém, o docker utiliza diversos  formatos e protocolos de comunicação, então a definição acima (`--host <host>`) faz com que haja uma garantia de que o protocolo `HTTP` já esteja sendo aceito pelo container.
### Usando `node:child_process`
O módulo `child_process` do node pode ser utilizado para executar e gerenciar comandos criando scripts de execução que realizam tarefas completas em contato direto com o sistema operacional, podemos então usá-lo para criar o script `wait-for-postgres.js`:
```node
// wait-for-postgres.js

// Utilizar commonJS é recomendados já que o script não irá passar por transpiling
const { exec } = require("node:child_process");

function checkPostgres() {
  // O comando exec do child_process executa um comando específico e uma função de callback para gerenciá-lo
  exec("docker exec postgres-dev pg_isready --host localhost", handleReturn);

  function handleReturn(error, stdout) {
    // Condição de parada: Encontrar "accepting connctions" na saída do comando 'docker exec'.
    if (stdout.search("accepting connections") === -1) {
      // Animação de loading
      process.stdout.write(".");
      // Chamada recursiva
      checkPostgres();
      return;
    }

    console.log("\n🟢 Postgres is ready\n");
  }
}

process.stdout.write("🔴 Awaiting for postgres");
checkPostgres();
```
### Integrando o script na execução do servidor local
Para integrar esse script na fila de execução do servidor local, modificamos o script "dev" no arquivo `package.json`:
```JSON
{
  "dev": "npm run services:up && npm run wait-for-postgres && npm run migrations:up && next dev",
  "wait-for-postgres": "node infra/scripts/wait-for-postgres.js"
}
```
## Estabilizando os testes locais
O próximo problema que surge é: Como rodar os [[Dia 15#Testes Automatizados|testes locais]] sem precisar passar por todo o processo de primeiro rodar o servidor local, esperar tudo estar pronto e só depois executar os testes? A primeira ideia é rodar ao mesmo tempo o `next dev` e o `jest --runInBand`, isso pode ser feito através do módulo node `concurrently`
### Usando `concurrently`

```bash
npm i -D concurrently
```

A partir dai já podemos utilizar o concurrently nos nossos scripts

```JSON
{
  "test": "concurrently 'next dev' 'jest --runInBand'"
}
```

Porém, alguma implementações são necessárias, primeiro, para facilitar a visualização dos comando e as operação das próximas flags podemos utilizar `--name` ou `-n` para nomear os comandos:

```JSON
{
  "test": "concurrently -n next,jest 'next dev' 'jest --runInBand'"
}
```

Agora,  já que nos testes o que nos interessa são as saídas do  [[Dia 15#Instalando o *Jest*|Jest]] podemos ocultar as saídas do [[Dia 3#Next.js|Next]] com a flag `--hide`

```JSON
{
  "test": "concurrently -n next,jest -h next 'next dev' 'jest --runInBand'"
}
```

Agora, o problema que surge é: o comando `next dev` roda indefinidamente, assim, precisamos adicionar a flag `--kill-others` ou apenas `-k` que encerrará os outros processos quando um deles for concluído

```JSON
{
  "test": "concurrently -n next,jest -h next -k 'next dev' 'jest --runInBand'"
}
```

Por último, precisamos obrigar o `concurrently` a apresentar o exit code igual ao do jest, já que é ele que nos interessa:

```JSON
{
  "test": "concurrently -n next,jest -h next -k -s command-jest 'next dev' 'jest --runInBand'"
}
```
### Rodando os serviços previamente
É importante notar que o funcionamento dos testes ainda depende de subir manualmente os serviços antes, assim podemos resolver com muita simplicidade

```JSON
{
  "test": "npm run services:up && concurrently -n next,jest -h next -k -s command-jest 'next dev' 'jest --runInBand'"
}
```
### Usando `async-retry` para construir um orchestrator
Agora, o obstáculo é garantir que o servidor local esteja rodando antes que os testes sejam executados, porém, isso não pode ser feito através do nosso `wait-for-postgres.js` já que ter o container do BD funcionando não nos garante que o servidor está de fato funcionando também, assim, uma solução possível é: Executar requests para o endpoint `/status` até que ele responda com sucesso, isso pode ser feito com um módulo chamado `async-retry`:

```bash
npm i async-retry
```

Agora, podemos utilizar  esse módulo para construir um orchestrator, uma ferramenta dedicada a coordenar a execução de processos complexos, no nosso caso, o orchestrator terá inicialmente apenas uma função: `waitForAllServices` que será assíncrona e esperará pela execução de funções filhas que avaliarão utilizando `async-retry` a disponibilidade de cada serviço, inicialmente, utilizaremos apenas a função filha `waitForWebServer` que se certifica que o servidor web está funcionando
```node
import retry from "async-retry";

async function waitForAllServices(){
  await waitForWebServer();

  async function waitForWebServer(){
    retry(fetchStatusPage(), {
      retries: 100;
    })

	async function fetchStatusPage() {
      const response = await                            fetch("http://localhost:3000/api/v1/status");
      if (response.status !== 200) {
        throw Error();
      }
    }
  }
}

export default {
  waitForAllServices
}
```
### Integrando com o Jest
O último passo é integrar o ``orchestrator`` com o jest fazendo que as suites de teste que dependem do servidor local só rodem quando ele estiver disponível, para isso, adicionamos a execução da função `waitForAllServices` no `beforeAll` das suites: 
```node
import orchestrator from "tests/orchestrator"

beforeAll(async () => {
  await orchestrator.waitForAllServices();
})
```
O último problema é: O Jest possui um test timeout padrão de 5 segundos, ou seja, se algo demorar mais que 5 segundos para executar ele simplesmente parará a suite e lançará um erro, para resolver isso definimos um tempo maior para a opção `testTimeout` no arquivo `jest.config.js`: 
```node
const jestConfig = createJestConfig({
  moduleDirectories: ["node_modules", "<rootDir>"],
  testTimeout: 60000,
});
```
