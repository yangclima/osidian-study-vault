Até agora, realizamos a combinação de dados entre duas relations usando a [[Instrução SELECT básica]], mais especificamente inserindo condições na clause `WHERE`, existe porém uma forma mais semântica de realizar essa operação, usando a família de operadores `JOIN`, dividido em dois principais subgrupos de operadores: os `OUTER JOIN` e os `INNER JOIN`.

Os `INNER JOIN` são usados, em geral, para combinar apenas registros que possuem uma determinada correspondência em duas tabelas e tem como principais declarações

1. `JOIN` ou`NATURAL JOIN`
2. `JOIN USING(<atributos>)` ou `NATURAL JOIN USING(<atributos)`
3. `JOIN ON <condition>` 

O `NATURAL JOIN` serve para combinar duas tabelas e e faz isso comparando os atributos dessas duas tabelas que possuem o mesmo nome, por exemplo:

```SQL
SELECT
    *
FROM
    candidates JOIN selection_process_applications
```

Essa query basicamente une as tabelas ``candidates`` e `selection_process_applicantions` através dos atributos em comum das relations, por exemplo, se ambas possuírem o atributo `Id`, esse `JOIN` combinará cada linha da primeira com a linha da segunda que possuir o mesmo valor para o atributo `id`, um dos problemas de usar o `JOIN` dessa maneira é que se houver mais de uma coluna com o mesmo nome entre as tabelas, ambas serão usadas como critério de comparação entre elas, o que pode acontecer é alguém acidentalmente adicionar uma coluna numa tabela com mesmo nome de um atributo da outra, isso pode ser resolvido com o uso da especificação `USING` que basicamente mantém o comportamento normal do `JOIN` mas especificando que atributo deve ser usado para a comparação, por exemplo:

```SQL
SELECT
    *
FROM
    candidates JOIN selection_process_applications USING(id)
```

O problema do `NATURAL JOIN` é que, normalmente, uma tabela referencia uma relação com outra não através do atributo `id`, mas algo como `user_id` ou `application_id`, assim, hoje em dia utilizamos muito mais o `INNER JOIN` especificando uma condição na clause `ON` que basicamente especifica a condição que o database usará para comparar e então mesclar as linhas, por exemplo:

```SQL
SELECT
    *
FROM
    candidates C JOIN 
    selection_process_applications A ON 
    C.application_id = A.id
```

No caso da query acima, a comparação é feita entre o atributo `application_id` de `candidates` e o atributo `id` de `selection_process_applications` e as linhas nas quais a condição for válida são mescladas e passam a reunir os atributos da linha de `candidate` e os de seu par em `selection_process_applications`.

O segundo subgrupo de operadores `JOIN` são os `OUTER JOIN`, usados quando queremos incluir todas as linhas de uma das tabelas, mesmo que não haja correspondências válidas na outra. Os 3 tipos de `OUTER JOIN` são:

1. `LEFT JOIN`
2. `RIGHT JOIN`
3. `FULL JOIN`

O `LEFT JOIN` faz tudo que um `INNER JOIN` faz, porém, retorna todas as linhas da primeira tabela mesmo que não encontre resultados compatíveis para elas na segunda, um exemplo é:

```SQL
SELECT 
    *
FROM
    users U
    LEFT JOIN 
    member_violations M
    ON U.id = M.user_id
```

Basicamente, ele retornará todas linhas da tabela `users`, e para aqueles que tiverem uma correspondência em `member_violations`, ele retornará os valores correspondentes dos atributos da tabela de violações, para os que não, esses atributos terão o valor `NULL`.

O `RIGHT JOIN` faz o contrário, ele retorna todas as linhas da segunda e equivale ao mesmo resultado de inverter os a ordem das tabelas na declaração de ``JOIN``, por exemplo:

```SQL
SELECT 
    *
FROM
    users U
    RIGHT JOIN 
    member_violations M
    ON U.id = M.user_id
```

essa query equivale a 

```SQL
SELECT 
    *
FROM
    member_violations M
    LEFT JOIN 
    users U
    ON U.id = M.user_id
```

Isto é, retornará todas as linhas de `member_violations`, mesclando aquelas que tiverem correspondência válida em `users` e retornando para essas os valores correspondentes dos atributos em `users` e para as que não, retornando todos os atributos da relação de usuários mas com o valor `NULL`. 

Poderíamos então pensar em fazer uma [[Aliases de tabela e operadores de conjunto|Operação UNION]] entre o `LEFT JOIN` e o `RIGHT JOIN`, mas existe um operador que faz exatamente isso, o `FULL JOIN`:

```SQL
SELECT 
    *
FROM
    member_violations M
    FULL JOIN 
    users U
    ON U.id = M.user_id
```

Como esperado, o resultado de uma query desse tipo é basicamente retornar todos os registros de ambas as tabelas, com todos os atributos de ambas mas para linhas sem correspondência atribuir os valores como `NULL`.