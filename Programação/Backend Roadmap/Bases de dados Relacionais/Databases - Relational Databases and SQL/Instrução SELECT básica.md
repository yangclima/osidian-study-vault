O SQL (Structured Query Language) é um linguagem declarativa que inclui internamente o [[Introdução e o modelo relacional|DDL e o DML]], definindo o Schema com instruções como `CREATE TABLE` e `DROP TABLE` e manipulando os dados com instruções como `SELECT`, `INSERT`, `DELETE` e `UPDATE`, possuindo ainda comandos que não se encaixam nessas linguagens como índices, constraints, triggers, transactions e muito mais.

A primeira instrução que veremos a `SELECT` cuja função é a busca de dados e estrutura básica é:

```SQL
SELECT A1, A2, ..., An
FROM R1, R2, ..., Rm
WHERE condition; -- Não Obrigatória
```

A leitura dessa query se dá começando pela clause `FROM` que indica em que relações iremos buscar os dados, e então a clause `WHERE` que filtra os dados das relations usando uma condição (Usar a query sem `WHERE` retornaria todos os dados, sem filtro) e por fim, a clause `SELECT` que define dentro das linhas encontradas nas relations especificadas no `FROM` e que passaram pelos filtros do `WHERE` que atributos queremos retornar como resultado da query.

O poder dessa linguagem se dá, como já vimos, pelo fato das queries serem fechadas e admitirem composição, de forma que podemos compor os dados de diferentes relações e retornar os dados de maneiras convenientes, um bom exemplo de query é:

```SQL
SELECT 
    users.name AS user_name, 
    role, 
    sector, 
    houses.name AS house_name
FROM 
    users, 
    houses
WHERE 
    users.house_id = houses.id AND 
    houses.name < > 'Lumina'
ORDER BY 
    users.name ASC;
```

Destrinchando-a temos uma pesquisa nas tabelas `users` e `houses`, filtradas pela condição de que as linhas retornadas devem ser apenas aquelas para as quais o atributo `house_id` da tabela `users` seja igual ao atributo `id` da tabela `houses` e que o atributo `name` da tabela `houses` seja igual a "Lumina", além disso, no fim, a clause `ORDER BY` define a ordenação dos dados devolvidos pela query, nesse caso, pela ordem alfabética dos nomes de usuário.

Não é o caso dessa, mas em algumas queries é importante evitar que hajam duplicatas no retorno da query o que é feito usando `DISTINCT`, por exemplo:

```SQL
SELECT DISTINCT
  users.name
FROM
  users, time_entries
WHERE
  time_entries.user_id = users.id AND 
  time_entries.clocked_in_at >= NOW() - INTERVAL '1 days';
```

Nessa query, estamos acessando as tabelas `users` e `time_entries` filtrando as linhas nas quais o atributo `user_id` de `time_entries` é igual ao atributo `id` de `users` e o atributo `clocked_in` de `time_entries` é uma data hora posterior ao momento atual menos o intervalo de um dia e das linhas que passaram pelo filtro, retornando os valores do atributo `name` de users sem duplicatas.

Um outro tipo muito útil de query usa regular expressions para pesquisar por matches nas relations, por exemplo:

```SQL
SELECT 
  *
FROM
  users
WHERE 
  name LIKE '%Lu%'
```

Aqui, acessamos a tabela `users` filtrando as linhas nas quais o atributo `name` dá match com a regex `%Lu%`  e retornando todos os atributos dessas linhas.

