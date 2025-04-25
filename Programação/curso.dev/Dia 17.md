No dia 17, começamos a ver alguns conceitos sobre bancos de dados e conteinerização para rodas serviços localmente mas de forma isolada, alem de garantir total padronização do funcionamento desses serviços, independente da máquina
# Banco de dados 
# DBMS
DBMS, ou *Database Management System* ou, traduzindo, SGBD (Sistema de Gerenciamento de Bando de Dados) é o software responsável por controlar e gerir toda a base de dados. A grande disputa/dúvida nesse ponto costuma ser Relacional vs. Não-relacional.
# Queries
Uma Query é basicamente uma consulta feita ao banco de dados no objetivo de alterar, ou obter dados armazenados nessa base de dados, para BD's relacionais normalmente essa queries são escritas em SQL, uma linguagem universal para isso, implementada pela maioria dos SGBD's.
# Migrations
Uma migration é um processo de gestão de mudanças na estrutura de um banco de dados, permitindo que o esquema do banco de dados evolua de forma controlada e versionada.

A escolha de um banco de dados para o seu projeto normalmente se concentra justamente na escolha de um conjunto DBMS + Biblioteca para queries + Sistema de migrations

> Para o tabnews esse conjunto foi PostgreSQL + pg-connector + node-pg-migrate
# Docker
Um grande problema que afetava inúmeros programadores e projetos de software era trabalhar com serviços como bancos de dados e devido a pequenas ou grandes diferenças de hardware e sistema operacional ter diferenças ou incompatibilidade ao trabalhar com aquele serviço em outro computador, esse problema foi resolvido com a popularização da virtualização, a criação de VM's (*Virtual machines*) possibilitando rodas o serviço num ambiente totalmente isolado, porém, com isso, surgiu um outro grande problema, VM's consumem muto armazenamento e poder de processamento, já que são literalmente uma execução simultânea de outro sistema operacional na sua máquina, foi aí que, utilizando features do linux que já existiam há algum tempo (*namespaces* e *cgroups*), foi criado o Docker, possibilitando executar o serviço num ambiente totalmente isolado, porém, sem toda a estrutura de um segundo sistema operacional
# Criando um container docker
Para criar um container, primeiro escrevemos um arquivo, nomeado por convenção com `compose.yaml` definindo as configurações dos containers.
```yaml
services:
  container:
    container_name: "container"
    image: "docker-image"
    ports:
      - "host:container"
```
## Docker image
O docker image é a compilação, binarização de uma docker file, um arquivo que define as configurações e comandos que vão formar o novo ambiente virtual, a docker image é então executada em um container docker, a imagens oficiais do docker estão disponível no docker hub.
## Subindo o container
Com as configurações já feitas no `compose.yaml`, subimos o container através do comando (No diretório do arquivo `compose.yaml`):
```bash
sudo docker compose up
```
Se o `compose.yaml` não estiver na mesma pasta que você, utilize a flag `--file` ou simplesmente `-f` para especificar o cominho. O comando acima, começa a rodar o container no terminal, de maneira assistida, mas usando a flag `--detach` ou `-d` nós passaremos a executá-lo de forma desacoplada do terminal, usando `--force-recreate` obrigamos o container a ser recriado
## Desativando um container
```bash
docker compose down
```
## Checando os processos
Podemos usar o comando a seguir para checar que containers estão em execução:
```bash
docker ps
```
usando a flag `--all` ou `-a` o comando acima exibirá mesmo os containers que não estão em execução. Um ponto a se atentar são s exit codes, que indicam os códigos de saída do último processo do terminal, sendo 0 um código de sucesso (The process terminated gracefully) e qualquer coisa maior que 0 (O números vão até 255), um código de erro.
## Exibindo os logs
Para exibir os últimos logs de um container usamos o comando a seguir:
```bash
docker logs <nome-do-container>
```
# Usando psql para se conectar no container
O psql é um client PostgreSQL via CLI e para conectar a um banco de dados rodando num container docker, criado com a imagem oficial do PostgreSQL  usamos o seguinte comando:
```bash
psql --host=localhost --username=postgres --port=5432
```