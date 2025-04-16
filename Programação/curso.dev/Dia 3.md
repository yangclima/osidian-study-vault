> "Para fazer uma torta de maçã do zero, primeiro você precisa criar o universo" - Carl Sagan

Hoje em dia, não precisamos reinventar a roda para fazer praticamente nada, temos diversos frameworks, ferramentas e linguagens de alto nível que podem nos auxiliar a alcançar nosso propósito.
# *Analisis  Paralisis*
Justamente devido a grande quantidade de ferramentas disponíveis para o desenvolvimento dos nosso projetos, muitas vezes nos encontramos no que chamamos de **Paralisia Analítica** (*Analisis  Paralisis*), travados perante a imensa gama de possibilidades que temos, nesses momentos é importante ter em mente que **um projeto imperfeito feito é melhor que um perfeito feito** e que existem milhares de maneiras de fazer um projeto sair do papel com qualidade, este não é um cainho único.
# Node Version Manager
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
# Node Package Manager
O npm, ou node package manager, é o mais famoso gerenciador de pacotes e projetos com node, e nos permite fazer o download e instalar inúmeras bibliotecas, pacotes e frameworks do ecossistema node.
## Criando projeto com npm
Criar um projeto node utilizando npm é muito simples, devemos utilizar o comando a seguir:
```bash
npm init
```
Ao executar esse comando, diversas perguntas aparecerão no seu  terminal, para personalizar o seu projeto, utilizando `Enter` fazemos com que os valores padrão sejam atribuídos 


