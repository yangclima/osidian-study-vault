**Continuous Integration** ou simplesmente CI é uma prática de desenvolvimento de software na qual os desenvolvedores integram as modificações do código regularmente em um repositório central o que permite a rápida identificação de erros, conflitos e bugs de forma antecipada.

A ideia é simples: sempre que fazemos um commit para o repositório compartilhado (GitHub, GitBucket, BitBucket...) uma ferramenta de CI faz o `build` do código e roda algumas rotinas configuradas pelo desenvolvedor (Testes automatizados, Linting de código, Linting de commits...) que garantem a integridade do código antes de colocá-lo em produção.

# GitHub Actions
Uma ferramenta de CI simples e poderosa são as **GitHub Actions**, fornecidas pelo GitHub. No projeto do `curso.dev` utilizaremos essa ferramenta para gerar um fluxo de CI/CD simples: 

> A partir da branch `default` do nosso repositório é aplicado o *Continuous Deployment* através das ferramentas da `Vercel` que observam a branch e sempre que um novo commit ou merge é feito nela, integra automaticamente as alterações no ambiente de produção, sabendo disso utilizamos alguma [[Dia 28#Estratégias de branching|estratégia de Branching]] para desenvolver correções e novas features para o nosso projeto, a ideia é então adicionar a esse fluxo a *Continuous Integration* a partir de rotinas padronizadas chamadas de `Actions` que garantirão o funcionamento, qualidade, estilo e integridade do nosso código antes de permitir que o merge seja feito na branch main.

Configurar uma nova `action` do GitHub é simples, precisamos apenas criar um arquivo `yaml` numa pasta `.github/workflows` na origem do nosso repositório, esse arquivo tem uma estrutura simples:

```yaml
name: <action_name>
on: <action_trigger>
  
jobs:
  <job>:
    name: <job_name>
    runs-on: <job_platform>
    
    steps: 
      - <step_1>
      - <step_2>
        with:
            <step_2_setting>
      - <step_3>
      - [...]
```

Cada `Action` é disparada por um ou mais gatilhos definidos através da propriedade `on`, como um `push`, um `pull_request` ou um conjunto de múltiplos gatilhos como um `array` `[push, pull_request]` e é formada por `jobs` que são propriamente os testes ou procedimentos que ela executará.

Cada `job` roda em uma máquina virtual configurada em uma plataforma predefinida pela configuração `runs_on`, por exemplo `ubuntu-latest`, `windows-latest` ou `macos-latest` e segue um passo a passo de execução definido com uma lista na propriedade `steps`.

## Testes Automatizados
Por exemplo, para criar um rotina que executa os [[Dia 15#Testes Automatizados|testes automatizados]], na plataforma `ubuntu-latest` ou seja, a versão mais recente do ``ubuntu`` podemos criar o arquivo `.github/workflows/tests.yaml`:

```yaml
name: Automated Tests
on: pull_request

jobs:
  jest:
    name: Jest Ubuntu
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20.20.0
      - run: npm ci
      - run: npm test
```

Cada step faz o seguinte:
- ``uses: actions/checkout@v4``: Usamos `uses` para nos referir a complementos disponibilizados por padrão pelo GitHub, nesse caso, `actions/checkout@v4` que é responsável por puxar o nosso código para dentro da máquina virtual que realizará o `job`.
- ``uses: actions/setup-node@v4``: Esse outro complemento, o `actions/setup-node@v4` é responsável por fazer o setup do `node` que setarmos usando a configuração `with/node-version`, nesse caso usamos a versão `20.20.0`. 
- ``run: npm ci``: Depois que nosso código está na máquina e o `node` foi configurado, podemos rodar comandos utilizando `run:` e utilizamos isso para baixamos as dependências do projeto usando `npm ci` que diferente do `npm install`, não resolve as dependências e as instala as a partir do que está explícito no arquivo `package-lock.json`.
- ``run: npm test``: Por fim, chegamos ao ponto alto do job, onde queríamos chegar e rodamos a nossa rotina de testes tal qual no nosso ambiente de desenvolvimento local, daí a importância de [[Dia 29#Estabilizando o ambiente local|estabilizar o ambiente local de testes]].

## Linting de Código
Além dos testes automatizados, uma rotina desejável pode ser realizar o **Linting de Código** o que já fazemos localmente com o [[Dia 10#Configurando o Prettier|Prettier]], visando garantir a formatação do nosso código de acordo com um estilo pré-definido independente das decisões de cada um em seu ambiente local, antes disso, podemos adicionar ao nosso projeto um ``Linter`` ainda mais poderoso e que além de formatação, garante que o código seguirá uma série de regras e padrões que garantirão a qualidade do código, em um projeto com [[Dia 3#Next.js|Next.js]] e Prettier e Jest, isso pode ser feito da seguinte maneira:

Primeiro rode o comando:

```bash
npm i -D eslint eslint-config-next eslint-config-prettier  eslint-plugin-jest
```

Então crie na origem do seu repositório o arquivo `eslint.config.mjs`:

```js
import { defineConfig, globalIgnores } from 'eslint/config';
import js from '@eslint/js';
import jest from 'eslint-plugin-jest';
import nextVitals from 'eslint-config-next/core-web-vitals';
import nextTs from 'eslint-config-next/typescript';
import prettier from 'eslint-config-prettier/flat';

const eslintConfig = defineConfig([
  // COnfigurações do Jest
  {
    files: ['src/tests/**/*.{ts,tsx, js, jsx}'],
    ...jest.configs['flat/recommended'],
  },
  // Configurações recomendadas do eslint
  {
    files: ['**/*.js'],
    ignores: ['src/tests/**/*.js'],
    plugins: {
      js,
    },
    extends: ['js/recommended'],
    rules: {
      'no-unused-vars': 'warn',
    },
  },
  // Regras padrão do Next 
  ...nextVitals,
  // Apenas se seu projeto usa Typescript 
  ...nextTs,
  // evita conflitos entre regras do Eslint e do Prettier
  prettier,
  globalIgnores(['.next/**', 'out/**', 'build/**', 'next-env.d.ts']),
]);

export default eslintConfig;
```

Por fim, adicionamos os  seguintes scripts ao `package.json`:

```json
 "lint:eslint:check": "eslint .",
"lint:eslint:fix": "eslint . --fix",
```

E então, para acionar o Linting do `Eslint` e do `Prettier` à nossa pipeline de CI utilizamos:

```yaml
name: Linting
on: pull_request

jobs:
  prettier:
    name: Prettier
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20.20.0
      - run: npm ci
      - run: npm run lint:prettier:check

  eslint:
    name: ESLint
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - uses: actions/setup-node@v4
        with:
          node-version: 20.20.0
      - run: npm ci
      - run: npm run lint:eslint:check
```

# Configurando `ruleset` da branch
Apesar de estarmos rodando as nossas rotinas de teste, até agora, nada nos impede de realizar o merge da alterações mesmo que os `jobs` falhem, por isso, é importante alterar as configurações do nosso repositório, fazemos isso indo nas configurações do repositório em `code and automation > rules > rulesets` e então clicando em `New ruleset > New branch ruleset` selecionando a branch default como target do ``ruleset`` e então selecionando as opções `Restrict deletions` que impedirá que a branch seja deletada, `Block force pushes` que impedirá que pushes com a tag `-f` ou `--force` sejam realizados contra a branch, `Require a pull request before merging` que exigirá a criação de uma `pull request` antes de realizar o merge contra a branch e por fim `Require status checks to pass` para exigir que todos os `jobs` terminem em sucesso para que o merge seja feito.