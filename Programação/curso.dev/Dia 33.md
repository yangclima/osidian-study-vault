No dia 33, continuando a saga sobre commits, que iniciamos no [[Dia 32]], queremos definir de forma final uma padronização para os nossos commits, adotando uma convenção amplamente utilizada na confecção da suas mensagens chamada de `Conventional Commits` 

>  Documentação do `Conventional Commits`: https://www.conventionalcommits.org/pt-br/v1.0.0/

Essa convenção usa um formato simples de commit, assim formado:

```
<type> [optional scope]: <message>

[optional body]

[optional footer]
```

No campo `<type>`, podemos utilizar diversos valores padronizados que visam especificar o tipo da mudança que o commit carrega, sendo esses valores baseados na convenção usada no projeto do `Angular`, sendo os principais:

1. `ci`: Mudanças nas configurações e scripts de CI
2. `build`: Mudanças que afetam o sistema de build ou dependências externas
3. `docs`: Mudanças somente na documentação
4. `feat`: Uma nova Feature para o projeto
5. `fix`: Uma correção de bug
6. `perf`: Uma mudança que visa melhorar a performance
7. `refactor`: Uma mudança que não adiciona, remove e nem corrige nada mas muda o código e/ou a implementação
8. `style`: Muda apenas o estilo do código, por exemplo a indentação, espaçamento ou uso de ponto e vírgula.
9. `test`: Adiciona testes que faltavam ou corrige testes existentes

Uma outra coisa interessante nessa convenção é que podemos utilizar `BREAKING CHANGE` para sinalizar que um commit adiciona uma mudança que quebra a implementação da interface pública da aplicação.

A ideia é então integrar essa padronização no nosso [[Dia 29#Implementando Continuous Integration|CI]], isto é, na nossa [[Dia 31#GitHub Actions|GitHub Action]] de Linting, permitindo o merge de uma PR somente quando todos os commits seguirem essa convenção e também impor isso de forma local para evitar problemas ao trabalhar em equipe.

Para integrar isso no CI podemos usar uma biblioteca open source chamada `commitlint` que disponibiliza um pacote ``npm`` que permite que utilizemos as suas ferramentas direto na linha de comando, o pacote `@commitlint/cli`. Entretanto, essa ferramenta é extremamente genérica e não possui nenhuma regra de linting por padrão, nesse caso, também utilizaremos o adaptador dessa biblioteca que contém as regras do `Conventional Commits`, isto é, o pacote `@commitlint/config-conventional`

> Documentação do `Commitlint`: https://commitlint.js.org/

Para adicionar os pacotes, utilizamos então o comando:

```bash
npm i -D @commitlint/cli @commitlint/config-conventional
```

E então criamos o arquivo de configuração do `commitlint`, o arquivo `commitlint.config.js` na raiz do nosso projeto:

```js
const commitlintConfig = {
  extends: ['@commitlint/config-conventional'],
};

export default commitlintConfig;
```

A partir daí já podemos testar se uma texto genérico qualquer se encaixa no nosso padrão de commits utilizando o comando:

```bash
echo "<texto-generico>" | npx commitlint
```

E então, é fácil integrar esse comando na nossa `GitHub Action` de Linting através de um `job` nomeado como `Commitlint`:

```yaml
commitlint:
    name: Commitlint
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
        with:
          fetch-depth: 0
      - uses: actions/setup-node@v4
        with:
          node-version: 20.20.0
      - run: npm install -D @commitlint/cli @commitlint/config-conventional
      - run: npx commitlint --from ${{github.event.pull_request.base.sha }} --to ${{github.event.pull_request.head.sha }} --verbose
```

Perceba que utilizamos o asset `fetch-depth` com o valor `0` na `action` `checkout@v4`, isso deve-se ao fato de que por padrão essa action baixa apenas o último commit para aumentar a performance, mas utilizando essa configuração ela passará a baixar todas.

O comando chave aqui é:

```bash
npx commitlint --from ${{ github.event.pull_request.base.sha }} --to ${{ github.event.pull_request.head.sha }} --verbose
```

Que, basicamente, roda o `commitlint` sobre cada mensagem de commit do histórico do git, partindo do commit de hash disponível na variável `github.event.pull_request.base.sha` (O primeiro commit da PR) até o commit cujo hash é dado na var `github.event.pull_request.head.sha`, ou seja, o último commit da PR.

Adicionando então essa `action` na pass check list da ruleset da branch ``main``, garantimos que só será possível realizar o merge de uma PR contra a `main`caso todos os seus commits passem com sucesso na checagem do `commitlint`, apesar disso, ainda não impedimos que um usuário faça, por acidente, um commit fora de padrão para a branch na qual estamos trabalhando o que pode levar à necessidade de correções constantes e problemas ao se trabalhar em equipe, por isso integraremos no nosso ambiente de desenvolvimento local uma ferramenta que automaticamente realizará a checagem dos nossos commits antes de permitir que um commit 
seja de fato efetuado.

Essa mecânica pode ser alcançada através de uma ferramenta presente por padrão no `git`, os scripts chamados de `hooks` e presentes, por padrão na pasta `.git/hooks`, porém, essa pasta não pode ser enviada para o repositório remoto e portanto, não conseguiríamos compartilha-los de forma simples para os desenvolvedores envolvidos, esse problema é resolvido utilizando o pacote `Husky`, uma solução open source.

> Documentação do `Husky`: https://typicode.github.io/husky/

Para instalar esse pacote usamos:

```bash
npm i -D husky
```

E então iniciamos sua configuração usando o comando:

```bash
npx husky init
```

Esse comando criará no diretório raiz do seu projeto um diretório `.husky` e adicionará aos seus scripts ``npm`` do `package.json` o script:

```json
"prepare": "husky"
```

Esse comando faz parte do ciclo de vida do comando `npm install` e permitirá que sempre que um novo contribuidor fizer o clone do repositório do projeto e instalar as dependências, ele automaticamente configure o funcionamento do `Husky`.

Após a inicialização do pacote, no diretório `.husky`, estará, por padrão um arquivo `pre-commit`, um dos tipos possíveis de hook, configurado com o comando `npm test`, entretanto, não é esse hook que no interessa no momento, então o deletamos e criamos em seu lugar o arquivo `commit-msg`, um hook que, como desejamos, executa sempre que realizamos o commit mas antes que o commit seja de fato adicionado ao histórico do ``git``, então, nesse arquivo, adicionamos o comando:

```bash
npx commitlint --edit $1
```

Que já funcionará, nos impedindo de criar commits fora do padrão definido pelo ``commitlint``. 

Como complemento final, podemos ainda adicionar à nossa pipeline de commit um helper chamado `commitizen` que nos fornece uma `CLI`, ou interface de linha de comando, que nos ajuda a escrever commits no padrão `conventional commits` de forma interativa.

> Documentação do `Commitizen`: www.npmjs.com/package/commitizen

Para instalar esse pacote, usamos o comando:

```bash
npm i -D commitizen
```

Depois disso, inicializamos o seu funcionamento utilizando:

```bash
npx commitizen init cz-conventional-changelog --save-dev --save-exact
```

O que adiciona o pacote `cz-conventional-changelog` às dependências de desenvolvimento e o seguinte objeto ao ``package.json``:

```json
"config": {
  "commitizen": {
    "path": "cz-conventional-changelog"
  }
}
```

Depois disso, podemos criar o seguinte script `npm`:

```json
"commit": "cz"
```

E nosso novo fluxo de commit consiste então em adicionar os arquivos em staged e então executar o comando:

```bash
npm run commit
```

Nesse momento a interface do `commitizen` surgirá e nos auxiliará na escrita do nosso commit conforme os padrões do `conventional commits`. 

Se, ocasionalmente, quisermos executar o commit sem executar os hooks, podemos usar:

```bash
git commit --no-verify
```

Ou simplesmente:

```bash
git commit -n
```

# `git rebase`

No contexto de manipulação de commits e estratégia de branching, o dia 33 também abordou o comando `git rebase`, um poderoso comando git que permite tanto a resolução de conflitos de merge quanto a edição de mensagens de commit.

No caso de um conflito de merge ocasionado por uma outra branch que foi mergeada contra a main depois que você já tinha criado a sua branch, você pode fazer o pull na main para atualizá-la, voltar a sua branch e rodar o comando a seguir:

```bash
git rebase main
```

O que abrirá uma interface que permitirá a aplicação sequencial dos commits da sua branch de tal maneira que te dará a opção de resolver os conflitos comparando o commit que gerou o conflito com o commit HEAD da main e escolher quais alterações aceitar ou não e resolver os conflitos, depois que os conflitos forem resolvidos adicionamos as files que estavam com conflito em staged e executamos o comando:

```bash
git rebase --continue
```

Depois disso, iremos de maneira automática para o próximo conflito ou finalizar o ``rebase`` abrindo o arquivo do commit para permitir a mudança da sua mensagem.

Uma outra utilidade desse comando é para alterar a mensagem de commits passados, por exemplo, se quisermos mudar a mensagem do penúltimo commit que fizemos, podemos usar o comando:

```bash
git rebase -i HEAD~2
```

Onde o `HEAD~2` significa 2 commits para trás do atual, da mesma forma, podemos com `HEAD~n` nos referir a `n` commits para trás do atual. Esse comando abrirá um arquivo listando todos os commits a partir do que você referenciou (`HEAD~2` no nosso exemplo), nesse arquivos, devemos substituir o `pick` que estará marcado, por padrão, em cada commit por `r` de `reword` nos commits cujas mensagens queremos alterar.