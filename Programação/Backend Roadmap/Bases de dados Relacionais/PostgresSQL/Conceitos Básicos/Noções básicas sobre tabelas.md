Uma tabela numa base de dados relacional segue a mesma ideia de uma tabela no papel, é formada por linhas e colunas, de modo que para cada tabela distinta temos um número e ordem fixa de colunas mas um número variável de linhas que reflete o número de registros armazenados e que não segue nenhuma ordem específica. É importante notar, que, por padrão, o SQL não define identificadores únicos para cada linha de modo que é possível, amenos que o contrário seja especificado, ter múltiplas linhas completamente idênticas.

Cada coluna possui um [[Tipos de Dados|tipo de dado]] que restringe o conjunto de valores que pode ser atribuído a uma coluna numa linha e fornece uma espécie de significado semântico a cada coluna.

Para criar uma tabela, utilizamos o comando `CREATE TABLE` seguindo a sintaxe:

```SQL
CREATE TABLE table_name (
    column_1 column_1_data_type,
    column_2 column_2_data_type,
    ....
)
```

A estrutura inicial dessa tabela poderá ser posteriormente [[Modificando Tabelas|modificada e complementada]] caso seja necessário e podemos também excluir uma tabela usando:

```SQL
DROP TABLE table_name
```

Esse comando retornará erro caso `table_name` não exista, para contornar esse comportamento no PostgreSQL podemos usar:

```SQL
DROP TABLE table_name IF EXISTS
```

