Assim como podemos inserir [[Instrução SELECT básica|instruções SELECT]] aninhadas no `WHERE`, isto é, [[Subqueries na clause WHERE]], podemos inserir também essas subqueries nas clauses `FROM` e `SELECT`, o que obtemos fazendo isso é basicamente que, passamos a operar nas relations e atributos calculados na query ao invés dos pré-existentes na database.

Por exemplo, podemos usar:

```SQL
SELECT
    name, processing_interval
FROM
    (
        SELECT
            C.name,
            C.created_at - A.created_at AS processing_interval,
            A.period
        FROM
            candidates C,
             selection_process_applications A
        WHERE
            C.application_id = A.id
    )
WHERE
    period >= 4;
```

Aqui basicamente, estamos buscando todos os atributos das linhas nas quais `period >= 4` da tabela temporária criada pela instrução da subquery, isto é, o `SELECT` mais externo não está buscando na tabela `selection_process_applications` mas no resultado gerado pelo `SELECT` aninhado, que, esse sim, busca dados na tabela real, note então que, primeiro a query gera a tabela virtual do `SELECT` interno e depois realiza nela uma query.

Quanto ao uso de queries aninhadas na clause `SELECT` temos como exemplo:

```SQL
SELECT
    name,
    (
        SELECT 
            COUNT(*) AS total_violations 
        FROM 
            member_violations M  
        WHERE 
            M.user_id = U.id 
    )
FROM
    users U
ORDER BY
    U.name ASC
```

Nessa query, para cada linha de `users` ele seleciona atributo `name` e o atributo `total_violations` obtido a partir de uma query de contagem na tabela de `member_violations`, o grande ponto a se entender aqui é que nessa query, o `SELECT` aninhado funcionará como um for loop, para cada linha da tabela de `users`, uma nova consulta será feita em `member_violations` para obter `total_violations`.

