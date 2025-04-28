O dia 22 aborda sobretudo as [[Dia 17#Migrations|Migrations]] de maneira a introduzir o conceito bem como utilizar o módulo `node-pg-migrate`.
# Para que servem as migrations
Como sempre, podemos pensar na definição de uma ferramenta com base no problema que ela resolve. Antes das migrations a única forma de levantar um banco de dados exatamente igual a um outro era anotar os comandos SQL utilizados para construir o primeiro e os repetindo, você já pode imaginar a margem de erro que isso abria,  foi para isso que surgiram as migrations, elas criam uma linha do tempo com as alterações feitas no BD, como se fossem scripts SQL. 

Os dois elementos principais das migrations são os **Arquivos de  migração** que definem a ordem das alterações e as próprias alterações e o **Framework de migração** que garante que cada arquivo seja executado na ordem certa e apenas uma vez.
## Scripts do `node-pq-migrate`
```json
"migration:create": "node-pg-migrate -m <diretório> create",
"migrations:up": "node-pg-migrate -m <diretório> --env-path .env.development up"
```