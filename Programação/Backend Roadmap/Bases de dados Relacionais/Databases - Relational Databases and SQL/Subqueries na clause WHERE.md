Já desenvolvemos os principais conceitos da [[Instrução SELECT básica]] os [[Aliases de tabela e operadores de conjunto]], porém, entramos muito rasamente na ideia [[Introdução e o modelo relacional|composicional]] das queries, de forma que daremos um passo maior nesse sentido usando as chamadas subqueries, aplicadas, inicialmente na clause `WHERE`.

Basicamente, na condição de filtragem que expressamos clause `WHERE` podemos usar instruções aninhadas de query para realizar buscas mais complexas, por exemplo:

```SQL
SELECT
    id, name
FROM 
    users
WHERE
   id IN (
        SELECT DISTINCT 
            user_id 
        FROM
            member_violations
   )
```


Basicamente, nessa clause where estamos utilizando o operador `IN` para estabelecer uma condição booleana que verifica se o atributo `id` de uma linha da relation `users` está presente no conjunto de dados retornado por uma subquery (Query aninhada) que retorna sem duplicatas todos os valores do atributo `user_id` da tabela `member_violations`, desse modo, a query como um todo retorna uma lista dos usuários que tem alguma violation registrada em seu nome.

Podemos ainda inverter essa condição para retornar uma listas dos usuários que não tem nenhuma violation registrada simplesmente usando o operador `NOT`:

```SQL
SELECT
    id, name
FROM 
    users
WHERE
   id NOT IN (
        SELECT DISTINCT 
            user_id 
        FROM
            member_violations
   )
```

Outro operador muito útil é o operador `EXISTS` que forma uma condição booleana cujo valor é verdadeiro se existe algum elemento na subquery operada, por exemplo:

```SQL
SELECT
    name,
    T1.clocked_out_at - T1.clocked_in_at AS duration
FROM
    time_entries T1,
    users
WHERE
    T1.is_valid = true AND
    NOT EXISTS (
        SELECT
            *
        FROM
            time_entries T2
        WHERE
            T2.is_valid = true AND
            T1.id <> T2.id AND
            T2.clocked_out_at - T2.clocked_in_at  >
                T1.clocked_out_at - T1.clocked_in_at  
    ) AND T1.user_id = users.id;
```

Essa query basicamente retorna o valor do atributo `name` da relation `users` e o valor da diferença entre os atributos `clocked_in_at` e `clocked_out_at` da tabela `time_entries` apelidando essa diferença como `duration` das linhas de `time_entries` filtradas com a condição de que a linha tenha o atributo `is_valid` como true e não exista **outra** linha nessa tabela, também com `is_valid = true` cuja diferença entre `clocked_in_at` e `clocked_out_at` seja maior que a dela, resumidamente, retornando a time entry de maior duração e o nome do usuário relacionado a ela.

Ademais, os operadores `ALL` e `ANY` também são muito interessantes para algumas queries mais complexas. O operador `ALL` basicamente determina uma condição verdadeira se a comparação sob a qual opera for verdadeira para todos os valores de uma subquery, por exemplo:

```SQL
SELECT
    name
FROM
    users U1
WHERE
    U1.created_at >= ALL (
        SELECT
            U2.created_at
        FROM
            users U2
    )
```

Basicamente, essa query retorna o valor do atributo `name`  da relation `users` das linhas filtradas pela condição de que o seu atributo `created_at` deve ser posterior ou igual a qualquer valor de qualquer linha do atributo `created_at`também da tabela `users`, isto é, basicamente retorna o `name` da última tupla criada na relation.

Quanto ao operador `ANY` ele define uma condição, verdadeira no caso em que a comparação operada seja verdadeira para pelo menos um valor do conjunto de dados operado, por exemplo:

```SQL
SELECT
    name
FROM
    users U1
WHERE
    NOT U1.created_at > ANY (
        SELECT
            U2.created_at
        FROM
            users U2
    )
```

De forma parecida com a anterior, essa query retorna o valor do atributo `name` das linhas da relation `users` filtradas pela condição de que não exista nenhuma linha na tabela `users` cujo atributo `created_at` seja posterior ao seu, isto é, para a qual `NOT U1.created_at >` seja verdadeira para algum valor da tabela.