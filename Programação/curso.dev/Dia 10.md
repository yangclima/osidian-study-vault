No dia 10, o assunto abordado é padronização e estilização de código, por quê isso se faz necessário e como resolver isso.
# Por quê padronizar o nosso código?
Ao programar, temos certa liberdade em alguns aspectos, como escolher se vamos usar tab ou espaço na indentação, qual vai ser o tamanho dessa indentação e muito mais, isso acaba gerando um certo resíduo no nosso código, é como se estivéssemos escrevendo à mão e esse resíduo fosse como a nossa caligrafia, cada programador deixa o seu código com a sua "letra", o problema é que em ambientes em que múltiplos devs trabalham, isso pode gerar uma enorme bagunça, além do que esse processo pode gerar mais um encargo no nosso cérebro (Esforçar-se para tem homogeneidade nesse aspecto), mas que pode facilmente ser resolvida adicionando algumas ferramentas no nosso [[Dia 2#Ambiente de Desenvolvimento|ambiente de desenvolvimento]].

Essas ferramentas são o **Editorconfig** e o **Prettier**, sendo o primeiro voltado a padronizar as configurações do editor, para quando estivermos criando nosso código, e o segundo para executar o Lint sobre nosso código, mesmo o já escrito, impondo sobre ele as nossas convenções: usar ou não ponto e virgula no final das linhas no JS, usar ou não espaços extras em funções e etc.
# Configurando o Editorconfig
A configuração do editor config é bem intuitiva, inclusive, algumas IDE's tem suporte nativo para ele, o que não é o caso do VS Code, onde precisamos baixar uma extensão para isso,  o restante da configuração é toda baseada nos arquivos `.editorconfig`, presentes no seu repositório.

Como a configuração do editor config pode ser diferente de um diretório para outro, o Editorconfig procura esses arquivos de configuração tanto no repositório atual quando nos repositórios acima dele e vai somando as configurações, só parando quando acabam os diretórios ou quando acha um arquivo de configuração com o argumento `root = true`, sendo assim, na raiz do nosso projeto, para configurar o Editorconfig devemos criar um arquivo `.editorconfig` e adicionar nele esse argumento.

O restante das configurações são aplicadas seletivamente, de tal forma que o programador pode, por exemplo, escolher aplicar configurações diferentes para diferentes linguagens de programação. Essa seleção é definida pelos seletores, que devem vir sempre antes de um bloco de configurações, o seletor `[*.js]`, por exemplo, aplica as configurações do
bloco que o segue a todos os arquivos JavaScript, e o seletor `[*]` aplica a todos os arquivos.

O Editorconfig tem uma infinidade de parâmetros editáveis, mas os principais são `indent_style` e `indent_size`, o padrão para JavaScript é usar espaço como estilo de indentação e um tamanho de indentação de 2 espaços. 

Assim, nosso `.editorconfig` básico  fica: 
```
root = true

[*]
indent_style = space
indent_size = 2
```

> Documentação do Editorconfig: https://editorconfig.org/
# Configurando o Prettier
O Prettier, diferente do editor config consegue fazer muito mais coisas por nós, consegue aplicar muito mais configurações e suporta muito mais parâmetros, tem uma configuração padrão extremamente completa e mesmo assim é uma ferramenta de estilização opinada, ou seja, podemos inserir muitos outros parâmetros ou editar os existentes, além disso ele é capaz de checar e também de editar automaticamente o nosso código, mesmo o que foi escrito antes de o configurarmos, fazendo tudo se encaixar nos padrões que definirmos.

Apesar de não precisarmos instalar a extensão do prettier no VS code obrigatoriamente, isso é muito conveniente, já que permite defini-lo como formatador padrão do aplicativo e quando setamos a configuração FormatOnSave para true sempre que salvarmos um arquivo o Prettier vai formatá-lo conforme os padrões.

Para adicionar de fato o Prettier no nosso projeto nós primeiro o instalamos como uma dependência de desenvolvimento, que consiste basicamente numa dependência que não é necessária para a execução da aplicação em produção mas é utilizada durante o seu desenvolvimento, fazemos isso através do seguinte comando:
```bash
npm install --save-dev prettier 
```
Ou, de maneira mais sucinta:
```bash
npm install -D prettier
```
O próximo é configurar os scripts que utilizaremos para executar os comandos para checar e para formatar os arquivos, fazemos isso adicionando as seguintes linhas nos scripts do `package.json`:
```json
"lint:prettier:check": "prettier --check .",
"lint:prettier:fix": "prettier --write .",
```
Assim, para checar a formatação executamos: 
```bash
npm run lint:check
```
E para executar a formatação para os arquivos usamos:
```bash
npm run lint:fix
```
Porém, um problema que pode surgir é, por exemplo, na execução do `lint:fix`  quando tivermos arquivos gerados pelo [[Dia 3#Next.js|Next.js]] na pasta `.next`, já que esses arquivos nem são editados por nós e nem vão para o GitHub, por isso, criamos o arquivo `.prettierignore`, num propósito muito semelhante ao arquivo `.gitignore`, ou seja, adicionaremos lá os arquivos e pastas que não queremos que o Prettier formate, com uma ressalva: Por padrão ele já ignora automaticamente o diretório `node_modules`, assim, nosso arquivo `.prettierignore` ficaria:
```
.next/
```

> Documentação do Prettier: https://prettier.io/