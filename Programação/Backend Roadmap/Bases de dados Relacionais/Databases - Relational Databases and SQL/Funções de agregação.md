Em algumas queries [[Instrução SELECT básica|SELECT]], queremos agrupar valores de uma tabela segundo uma determinada condição ou atributo, imagine por exemplo que queremos encontrar o número de faltas de um membro na tabela `member_violations`, as funções que permitem esse tipo de busca chamam-se `AGREGATION FUNCTIONS` e eles permitem justamente resumir as linhas segundo alguma especificação, são elas:

1. `MIN` - Busca o valor mínimo de um atributo
2. `MAX` - Busca o valor máximo de um atributo 
3. `SUM` - Busca a soma dos valores de um atributo
4. `AVG` - Busca a média dos valores de um atributo
5. `COUNT` - Busca o número de linhas 

Então, por exemplo a query:

```SQL
SELECT
    MIN(period)
FROM
    selection_process_applications
```

Retornará o menor valor do atributo `period` presente nas linhas de `selection_process_applications`.

```SQL
SELECT
    MAX(period)
FROM
    selection_process_applications
```

Retornará o maior valor do atributo `period` presente nas linhas de `selection_process_applications`.

```SQL
SELECT
    AVG(period)
FROM
    selection_process_applications
```

Retornará o valor médio do atributo `period` presente nas linhas de `selection_process_applications`.

```SQL
SELECT
    SUM(period)
FROM
    selection_process_applications
```

Retornará a soma dos valores do atributo `period` presentes nas linhas de `selection_process_applications`.

```SQL
SELECT
    COUNT(*)
FROM
    selection_process_applications
```

Retornará o número de linhas de `selection_process_applications`. Enquanto

```SQL
SELECT
    COUNT(DISTINCT period)
FROM
    selection_process_applications
```

Retornará o número de valores distintos presentes para o atributo `period` em `selection_process_applications`.

Mas e quanto a de fato agregar os valores, agrupá-los segundo alguma condição e atributo? Isso pode ser feito usando a clause `GROUP BY`, por exemplo:

```SQL
SELECT
    U.name,
    COUNT(*)
FROM
    users U JOIN member_violations V ON U.id = V.user_id
GROUP BY
    U.name
```

Basicamente, essa query retorna o número de violations para cada usuário para qual existe alguma violation, isto é, ele agrupa as linhas usando o atributo `name` de `users` e conta a quantidade de linhas onde cada `name` aparece no resultado do `JOIN`.

Pode ainda ser adicionada uma clause `HAVING` que faz uma filtragem dos grupos, restringe a atuação do `GROUP BY`, filtra de forma semelhante ao `WHERE`, por exemplo:

```SQL
SELECT
    U.name,
    COUNT(*)
FROM
    users U JOIN member_violations V ON U.id = V.user_id
GROUP BY
    U.name, V.source
HAVING
    V.source = 'automatic'
```

Nesse caso, o resultado é o mesmo, com a diferença de que aqui, só serão consideradas as linhas de `member_violations` que possuem `source = 'automatic'`.


