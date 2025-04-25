# ISO 8601
A ISO 8601 é uma norma internacional para a representação de data e hora, definindo o formato padrão como `YYYY-MM-DDTHH:mm:ssZ` onde o `T` define a transição do espaço dedicado a data para o dedicado a hora e o `Z` define a timezone zulu, do horário militar padrão, ou seja UTC+00.

Para gerar a hora atual nesse formato em JavaScript usamos: 
```javascript
const updatedAt = new Date().toISOString
```
# Snake case
Por convenção, uma API rest devem retornar objetos JSON com propriedades nomeadas seguindo a snake_case, ou seja, com todas as palavras escritas em letras minúsculas e separadas por underlines ( _ ). e. g. `esta_propriedade_esta_escrita_em_snake_case`.
# Red, green, refactor

![[Pasted image 20250422142845.png]]
Red, green e refactor são estados que ajudam a guiar o [[Dia 15#Test Driven Development (TDD)|TDD]], definindo que ele deve ser dividido em 3 estágios, a criação de testes, que inicial mente gerarão exceptions (Red), a escrita do código para satisfazer os testes, fazendo com que os test cases passem (Green) e a refatoração para melhorar o código escrito (Refactor).
# Stats do banco de dados
No PostgreSQL podemos acessar alguns stats relacionados à saúde do banco de dados através de queries executadas, veja:
## Versão 
A versão do banco de dados pode ser acessada de duas maneiras, a versão completa com:
```SQL
SELECT version();
```
Ou a versão simplificada com:
```SQL
SHOW server_version;
```
## Conexões máximas
O máximo de conexões do banco de dados pode ser acessado usando o seguinte comando:
```SQL
SHOW max_connections;
```
## Conexões abertas
As conexões abertas de um banco de dados podem ser acessadas usando o seguinte comando:
```SQL
SELECT count(*)::int FROM pg_stat_activity WHERE datname='DBname'
```
Essa query pode ser construída no JS usando template strings, e trazendo para a query o `DBname` usando variáveis de ambiente, porém queries parametrizadas como essa podem ser uma grave falha de segurança por conta do SQL Injection, onde alguém pode tentar ter acesso ao banco de dados usando de  um comando SQL não sanitizado, o modulo  [[Dia 18#Estrutura básica do `pg`|pg]] tem por padrão uma maneira mais segura de usar queries parametrizadas: 
```javascript
const databaseName = process.env.POSTGRES_DB
const openedConnectionsResult = database.query({
  text: "SELECT count(*)::int FROM pg_stat_activity WHERE datname= $1 ;",
  values: [databaseName]
})
```
