Além de fazer a formatação e linting do nosso código utilizando [[Prettier]] e [[Eslint]], é essencial para projetos profissionais de código ter também uma padronização no que se refere as mensagens de commit para permitir uma rápida identificação do conteúdo que cada um agrega, um padrão muito adotado hoje para isso é o chamado [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)
Para utilizar esse padrão sem depender do fator humano é extremamente útil construir um Pipeline local de commits que vai desde auxiliar a seguir o formato mencionado a impedir que commits fora do padrão sejam feitos, essa pipeline pode ser construída usando os pacotes `Husky` (Uma ferramenta que Controla e Permite a criação de scripts que serão executados sempre que tentarmos fazer um commit), `Commitizen` (Uma ferramenta de linha de comando que auxilia a criação de mensagens de commit) e `Commitlint` (Uma ferramenta de linha de comando que faz o linting de mensagens de commit).

O primeiro passo é adicionar o `Commitlint` o que pode ser feito usando:

```bash
npm i -D @commitlint/cli @commitlint/config-conventional
```

Depois, criamos o arquivo de configuração, onde definimos as regras que o `commitlint` deve seguir ao fazer o linting dos nossos comandos, o arquivo `commitlint.config.js`:

```js
const commitlintConfig = { 
  extends: ['@commitlint/config-conventional'] 
};

export default commitlintConfig;
```

O próximo passo é então instalar o `Husky` no nosso projeto :

```bash
npm i -D husky
```

Agora, precisamos configurá-lo para fazer o linting da mensagem de commit usando o `commitlint`, a sua inicialização é feita através do comando:

```bash
npx husky init 
```

A partir disso uma pasta `.husky` será criada e lá que criaremos os scripts que queremos que sejam executados antes da confirmação do commit, funciona da seguinte maneira: Quando tentarmos fazer um commit o `Husky` vai detectar e executar os scripts da pasta `.husky`, se nenhum retornar erro, o commit será efetuado, o commit que criaremos será então:

```
npx commitlint --edit $1
```

Onde `$1` é o argumento que o `Husky` irá passar para o script e que consiste basicamente no local do arquivo `.git/COMMIT_EDITMSG` onde está a mensagem de commit que será analisada, se a mensagem bater com o padrão, o script retorna sucesso e o commit é feito.

Por fim, para facilitar nossa vida, instalamos o `commitizen`:

```bash
npm i -D commitizen cz-conventional-changelog
```

Para finalizar, precisamos adicionar o seguinte no nosso `package.json`:

```json
"config": {
  "commitizen": {
    "path": "cz-conventional-changelog"
  }
}
```

E por praticidade, o seguinte script:

```json
"commit": "cz"
```

E podemos então executar o comando `npm run commit` sempre que formos fazer um commit.