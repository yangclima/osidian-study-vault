Agora que já sabemos os [[Introdução e o modelo relacional|conceitos iniciais do modelo relacional]] e o básico da [[Instrução SELECT básica|instrução SELECT]] adicionaremos mais algum poder de query utilizando aliases de tabela e os operadores de conjunto.

As duas principais funções das aliases de tabela são tornar as queries mais legíveis e permitir renomear relações quando precisamos operar sobre duas instâncias da mesma relação, quanto a primeira função conseguimos escrever a query de maneira mais concisa adotando:

```SQL
SELECT 
    U.name AS user_name, 
    role, 
    sector, 
    H.name AS house_name
FROM 
    users U, 
    houses H
WHERE 
    U.house_id = H.id AND 
    H.name = 'Lumina'
ORDER BY 
    U.name ASC;
```

Quanto a segunda função podemos operar entre duas instâncias de uma mesma tabela, por exemplo:

```SQL
SELECT
    U1.id, U1.name
FROM 
    users U1, users U2
WHERE 
    U1.name = U2.name AND
    U1.id > U2.id
```

Aqui, fazemos a query sobre duas instâncias `U1` e `U2` da tabela de `users` filtrando as linhas onde o atributo `name` da primeira é igual o da segunda e onde o `id` de `U1` é maior que o de `U2` (Isso é um artefato usado por que usando essa query, acaba havendo  uma duplicação dos resultados já que duas tuplas iguais mas com ordens distintas são consideradas linhas diferentes e então aparecem duas vezes) e retornando, por fim, os atributos `name` e `id` das linhas encontradas, uma query que pode então ser usada para encontrar duplicatas de `name` na tabela users.

Quanto aos operadores de conjunto, temos os operadores `union` ($\cup$), `intersect` ($\cap$) e `except` ($-$) eles basicamente operam sobre o resultado de queries como os operadores matemáticos equivalentes atuam sobre conjuntos, por exemplo

```SQL
SELECT name FROM candidates 
UNION
SELECT name FROM selection_process_applications
```

A query acima basicamente roda uma busca na relation `candidates` selecionando o seu atributo `name` e uma busca na relation `selection_process_applications` selecionando o seu atributo `name` e executando o operador de união entre os resultados, isto é, retornando uma lista com os valores da primeira busca e da segunda busca, além disso, por padrão (Pelo menos no Postgres) ele faz a ordenação dos resultados e remoção automática de duplicatas, se necessário evitar essa remoção de duplicatas, podemos usar `UNION ALL` ao invés de `UNION`.

O próximo operador é o `intersect`, por exemplo:

```SQL
SELECT 
    C.name 
FROM 
    candidates C 
WHERE 
    C.selection_process_id = '4b9d8f5'
INTERSECT
SELECT 
    C.name
FROM 
    candidates C
WHERE
    C.selection_process_id = '1e47d4e1' 
```

Nessa query, basicamente buscamos por todas as linhas da relation `candidantes` onde o atributo `selection_process_id` é igual a `4b9d8f5` e por todas as linhas dessa mesma relation onde o mesmo atributo tem o valor `1e47d4e1` retornando em ambos os casos apenas o atributo `name` e executamos uma operação de `INTERSECT` entre os resultados das queries, que retorna apenas os valores de `name` que estão tanto no resultado da primeira query quanto no da segunda, ou seja, candidatos que se candidataram a ambos os processos seletivos.

Por fim, como exemplo do operador de `EXCEPT` temos:

```SQL
SELECT 
    name 
FROM 
    users
EXCEPT
SELECT DISTINCT 
    U.name 
FROM 
    users U, member_violations V 
WHERE 
    U.id = V.user_id
```

Aqui, basicamente estamos buscando a lista de valores do atributo `name` de todas as linhas da tabela `users` e selecionando todos os valores do atributo `name` sem duplicatas da relation `users` cujo atributo `id` coincide com o atributo `user_id` de alguma linha da relation `member_violations` e então, sob o resultado das queries, executando o operador `EXCEPT` que retornará então apenas os valores que apareceram no resultado da primeira query mas não apareceram no resultado da segunda, isto é, usuários que nunca receberam faltas.

Algo a se atentar é que, para funcionamento dos operadores de conjunto:

1. Ambas as queries precisam retornar o mesmo número de colunas
2. As colunas correspondentes precisam ter o mesmo tipo de dados