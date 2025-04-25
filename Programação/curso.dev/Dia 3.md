No dia 3, vimos algumas das ferramentas que estarão presentes no nosso [[Dia 2#Ambiente de Desenvolvimento|ambiente de desenvolvimento]], bem como algumas noções sobre a construção de projetos.

> "Para fazer uma torta de maçã do zero, primeiro você precisa criar o universo" - Carl Sagan

Hoje em dia, não precisamos reinventar a roda para fazer praticamente nada, temos diversos frameworks, ferramentas e linguagens de alto nível que podem nos auxiliar a alcançar nosso propósito. 
# *Analisis  Paralisis*
Justamente devido a grande quantidade de ferramentas disponíveis para o desenvolvimento dos nosso projetos, muitas vezes nos encontramos no que chamamos de **Paralisia Analítica** (*Analisis  Paralisis*), travados perante a imensa gama de possibilidades que temos, nesses momentos é importante ter em mente que **um projeto imperfeito feito é melhor que um perfeito feito** e que existem milhares de maneiras de fazer um projeto sair do papel com qualidade, este não é um cainho único.
# Node Version Manager (nvm)
Podemos utilizar o nvm, ou Node Version Manager para gerenciar a utilização do node (Execução nativa de JavaScript) nos nossos projetos, garantindo um nivelamento da versão do node para todos os envolvidos no projeto. 
## Listar versões disponíveis
O comando `ls`do nvm mostra todas as versões disponíveis para a instalação, o ideal é escolher versões LTS (*Long Time Support*):
```bash
nvm ls
```
## Instalar uma versão
Para instalar uma versão específica do node utilizamos o seguinte comando do nvm:
```bash
nvm install <version>
```
## Escolhendo a versão padrão
Muitas versões diferentes do node podem ser instaladas através do nvm e existir no seu computador simultaneamente, por isso precisamos definir uma versão padrão, dessa forma não precisaremos definir a versão do node sempre que abrirmos um novo terminal:
```bash
nvm alias default <version>
```
## Arquivo `.nvmrc`
É comum utilizar na raiz de um projeto diversos arquivos de configuração que nos indicarão características importantes sobre o desenvolvimento e execução desse projeto, é muito comum que o nome desses arquivos sejam iniciados em `.`, por serem arquios "ocultos" e terminarem em `rc`, que significa "*run control*" ou controle de execução, para o nvm, seu arquivo é o `.nvmrc` que indica a versão correta do node para o projeto:
```plaintext
<version>

```
**OBS**: É importante ter uma linha em branco no final.
# Node Package Manager (npm)
O npm, ou node package manager, é o mais famoso gerenciador de pacotes e projetos com node, e nos permite fazer o download e instalar inúmeras bibliotecas, pacotes e frameworks do ecossistema node.
## Criando projeto com npm
Criar um projeto node utilizando npm é muito simples, devemos utilizar o comando a seguir:
```bash
npm init
```
Ao executar esse comando, diversas perguntas aparecerão no seu  terminal, para personalizar o seu projeto, utilizando `Enter` fazemos com que os valores padrão sejam atribuídos aos campos (Ou utilizando a flag `-y`). A partir das respostas o npm criará um arquivo de configuração do projeto, o `package.json` que conterá diversas informações sobre o projeto, tais como título, autor, e o mais importante: **as dependências do projeto**.
## Instalando um pacote
Para instalar um pacote no nosso projeto usamos `npm install` veja:
```bash
npm install <packacge>@<version>
```
Também, é  possível instalar o pacote sem escolher uma versão específica, instalando assim automaticamente a versão mais recente:
```bash
npm install <package>
```
Se estivermos reinstalando os pacotes num projeto que acabamos de baixar pomos usar o comando sem nenhum argumento:
```bash
npm install
```
Assim instalamos todas as dependências presentes no arquivo de configuração do projeto (`package.json`).

# Next.js
Next.js é um framework React usado para construir aplicações web full-stack, permitindo o desenvolvedor a utilizar o react para gerar a interface do usuário e o next para algumas funcionalidades adicionais, como compilação e roteamento.
```bash
npm install next
```

> A versão utilizada no projeto do clone do tab-news é a `13.1.6`.

>O link para a documentação do next é https://nextjs.org/docs.

# React
React é uma biblioteca JavaScript que permite a criação de interfaces gráficas de usuário (GUI) desacopladas (Componentizadas) e dinâmicas para aplicações web e mobile.
```bash
npm install react
```

> A versão utilizada no projeto do clone do tab-news é a `18.2.0`.

>O link para a documentação do next é https://react.dev/learn.
# React-dom
Como o react é capaz de renderizar diversos tipos de conteúdos em diferentes plataformas diferentes, essa renderização foi sabiamente dividida em módulos, o módulo do react que trabalha com a renderização no navegador é o `react-dom`.
```bash
npm install react-dom
```

> A versão utilizada no projeto do clone do tab-news é a `18.2.0`.