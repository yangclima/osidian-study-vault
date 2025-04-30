O dia 27 apresenta mais alguns tópicos sobre o controle e gestão de branches, além de algumas ferramentas úteis para melhoria de qualidade de vida ao trabalhar com o `curl` (`watch` e `jq`).
# Deletando uma branch
Para deletar uma branch, usamos o comando
```bash
git branch -d <branchName>
```
# Realizando o merge
O merge é ação de unir, mesclar as alterações feitas em uma branch em outra branch, isso pode ser feito com o comando 
```bash
git merge <branchName>
```
O comando acima faz o merge da branch especificada (Source branch) na branch atual (Target branch), o merge também pode ser feito através de uma Pull Request ou PR, onde enviamos a branch para o repositório remoto e criamos uma solicitação de merge pelo GitHub.
# Recuperando uma branch
Em alguns casos, por confusão ou falta de atenção, podemos acabar deletando uma [[Dia 26|Branch]] que continha alguma modificação importante que ainda não tinha passado pelo merge, por mais que isso possa ser assustador, é simples de resolver, como vimos, a branch é apenas um ponteiro apontando para um commit, logo, mesmo apagando a branch os commits dessa branch ainda estarão lá, logo, tudo que você precisa fazer é criar uma nova branch apontando para esse commit, isso pode ser feito com o comando
```bash
git checkout -b <branchName> commit <commitHash>
```
Para descobrir o hash do commit você pode utilizar o comando
```bash
git reflog
```
# `jq`
`jq` é uma biblioteca que vem por padrão em muitos sistemas operacionais baseados em Unix e que serve para exibir objetos JSON de forma mais agradável, assim podemos usá-lo da seguinte forma:
```bash
curl <URL> -s | jq
```
Obtendo assim a resposta da URL exibida de forma mais inteligível.
# `watch`
Podemos utilizar o comando `watch` para realizar várias vezes um mesmo comando, por exemplo:
```bash
watch -n 5 'curl <URL> -s | jq' 
```
repetirá o comando `curl <URL> -s | jq` a cada 5 segundos.