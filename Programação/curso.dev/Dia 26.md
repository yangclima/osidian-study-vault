O dia 26 foi centrado em explicar e definir os principais comandos e modos de utilizações das branches no Git, além de introduzir a uma compreensão mais concreta do que realmente se trata o ambiente de homologação.
# Os 3 níveis de compreensão
Existem 3 níveis de compreensão acerca de como funcionam as branches no [[Dia 5#Versionando com Git|Git]], o primeiro nível, nos leva a pensar nas branches como cópias do nosso projeto, pastas diferentes, como se copiássemos o nosso projeto e nessa cópia fizéssemos as alterações que pretendemos depois levar a nossa branch principal, porém, imagine o quão custoso em questão de armazenamento isso seria. O segundo nível de compreensão é alcançado ao pensarmos em [[Dia 5#Como o Git funciona|como o git funciona]] e que portanto, uma branch seria uma cópia dos blobs relativos a cada commit e consequentemente, uma cópia da linha do tempo do nosso repositório, o que se aproxima da realidade, porém só entendemos de fato o funcionamento das branches no 3 nível de compreensão: Na verdade, só existe uma linha do tempo e a branch é basicamente um ponteiro que aponta para um commit específico, permitindo que a branch main aponte para um commit passado mas um outra branch aponte para um commit atual, e até mesmo a branch remota aponte talvez, para outro commit.
# Gerenciando as branches
## Visualizando as branches disponíveis 
As branches disponíveis no seu repositório local podem ser visualizadas utilizando o comando `branch`:
```bash
git branch
```
O comando exibirá todas as branches existentes atualmente com um asterisco ao lado da branch atualmente ativa.
## Trocando entre branches
Para trocar entre branches, podemos utilizar o comando `switch`, um comando recente e especializado para essa tarefa
```bash
git switch <branchName>
```
Ou, utilizar o comando `checkout` que é muito mais antigo e que acaba sendo um pouco polêmico por realizar diversas funções no Git:
```bash
git checkout <branchName>
```
## Criando uma branch
Para criar uma branch podemos utilizar o próprio comando branch:
```bash
git branch <newBranchName>
```
Criando a branch com esse comando, você precisará ainda trocar de branch após a criação, porém, para ter mais agilidade podemos usar o comando:
```bash
git checkout -b <newBranchName> 
```
Esse comando criará a branch e automaticamente tornará a nova branch como a branch ativa.
## Fazendo o push de uma nova branch
Para fazer o push de uma nova branch precisamos utilizar o comando a seguir: 
```bash
git push --set-upstream origin <branchName>
```
# Utilizando o pipe
O pipe `|` é um operador que pode ser utilizado para passar  resultado de um comando para o outro como argumento, por exemplo, o comando:
```bash
curl <url> -s | python -m json.tool
```
Passa o resultado da requisição feita pelo `curl` para o python que utiliza o módulo `json.tool` para exibir o conteúdo de uma maneira mais organizada, ou seja, com o `json` endentado.
# Lei de Linus
> Given enough eyeballs all bugs arre shallow

> Dado um suficiente números de olhos, todos os bugs são superficiais