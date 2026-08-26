As colunas são componentes fundamentais no PostgreSQL e são usadas para armazenar os dados e definir os [[Tipos de Dados|tipos de dados]], constraints e outras propriedades.

Quando criamos uma tabela podemos cometer erros e, além disso, os requisitos da aplicação a qual o banco de dados serve podem mudar, justificando a existência de múltiplos comandos que permitem alterar uma tabela, seus dados e estrutura.

# Adicionando ou removendo um coluna
Para adicionar uma coluna numa tabela, utilizamos um comando cuja sintaxe é:

```SQL
ALTER TABLE table_name 
    ADD COLUMN column_name data_type
```

podemos ainda incluir um valor padrão para a linha:

```SQL
ALTER TABLE table_name 
    ADD COLUMN column_name data_type DEFAULT default_value
```

Ou memo constraints:

```SQL
ALTER TABLE table_name 
    ADD COLUMN column_name data_type CHECK (constraint_expression)
```

Ou para remover:

```SQL
ALTER TABLE table_name DROP column_name 
```

Se existirem constraints associadas a essa coluna nessa tabela, essas constraints serão excluídas automaticamente, porém, se uma foreign key externa a referenciar os objetos externos não serão silenciosamente deletados, a menos que usemos:

```SQL
ALTER TABLE table_name DROP column_name CASCADE
```

# Adicionando ou removendo uma constraint 
Para adicionar uma constraint numa tabela usamos:

```SQL
ALTER TABLE table_name 
    ADD CHECK (constraint_expression)
```

```SQL
ALTER TABLE table_name 
    ADD CONSTRAINT constraint_name UNIQUE (column_name)
```

```SQL
ALTER TABLE table_name 
    ADD FOREIGN KEY (column_name) REFERENCES external_table_name
```

```SQL
ALTER TABLE table_name
	ALTER COLUMN column_name SET NOT NULL
```

E para remover:

```SQL
ALTER TABLE table_name
    DROP CONSTRAINT constraint_name 
```

```SQL
ALTER TABLE table_name
    ALTER COLUMN column_name DROP NOT NULL
```

# Mudando o valor padrão de um coluna
Para acionar um valor padrão para uma coluna de tabela usamos:

```SQL
ALTER TABLE table_name ALTER COLUMN column_name SET DEFAULT default_value
```

E para remover, usamos:

```SQL
ALTER TABLE table_name ALTER COLUMN column_name DROP DEFAULT
```

# Mudando o tipo de dado de uma coluna
Para modificar o tipo de dado de uma coluna:

```SQL
ALTER TABLE table_name ALTER COLUMN column_name TYPE new_data_type;
```

# Modificando o nome de uma coluna
Para modificar o nome de uma coluna, usamos:

```SQL
ALTER TABLE table_name RENAME COLUMN colum_name TO new_column_name
```

# Modificando o nome de uma tabela
Para modificar o nome de uma table, usamos:

```
ALTER TABLE table_name RENAME TO new_table_name
```