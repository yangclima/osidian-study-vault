O dia 23 aborda mais alguns conceitos importantes no tópico [[Dia 22#Para que servem as migrations|Migrations]].
# Dry Run vs. Live Run
Dry Run é um termo comum na programação e se refere a rodar serviços no modo de teste, sem implicações reais, para testar o comportamento daquele determinado serviço, o Live Run, ao contrário, se refere a executar realmente o serviço.
# Node `join`
As vezes podemos ter problemas com os sistemas de arquivos a depender do seu sistema operacional já que o sistema de arquivo windows é diferente dos SO's baseados em Unix, em node resolvemos isso com a função `join` do módulo `node:path`:
```js
import { join } from "node:path";

const universalPath = join("dirPai", "dirFilho", "file.ext");
```
# API programática do `node-pg-migrate`
Uma maneira de rodar as nossas migrations é utilizando a API programática do `node-pg-migrate`, no seguinte formato:
```js
import migrationRunner from "node-pg-migrate";

const migrations = migrationRunner({
  dataBaseUrl: string,
  dryRun: boolean,
  dir: string,
  direction: enum["up", "down"],
  verbose: boolean,
  migrationsTable: string 
})
```