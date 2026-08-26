Existe um tipo especial de valor no SQL, o `NULL`, que equivale não ao zero mas ao desconhecido, o não registrado, representando a ausência de um valor no banco de dados.

Um problema comum de ocorrer, por exemplo é quando tentamos realizar comparação como maior que, igual e etc com valores `NULL`, o `SQL` tem uma característica chamada de lógica trivalente, no qual qualquer condição tem como saída um dos seguintes 3 valores:

1. `TRUE`
2. `FALSE`
3. `UNKNOW`

E `UNKNOW` é o valor padrão para qualquer comparação que envolve `NULL`, de modo que um query como:

```SQL
SELECT
    U.id,
    U.name
FROM
    users U LEFT JOIN member_violations V ON U.id = V.user_id
WHERE
   V.user_id = NULL
```

Nunca retornará nenhum valor, por que nenhuma vez `V.user_id = NULL` retornará false ou true, mas sempre `UNKNOW`. Existe porém, um operador para lidar com essa situação:

```SQL
SELECT
    U.id,
    U.name
FROM
    users U LEFT JOIN member_violations V ON U.id = V.user_id
WHERE
   V.user_id IS NULL
```

Nesse caso, a query retornará nome e id dos usuários que possuem nenhuma violations registrada.