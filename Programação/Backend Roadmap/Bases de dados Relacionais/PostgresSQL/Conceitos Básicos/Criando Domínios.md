Domínios são essencialmente [[Tipos de Dados]] compostos definidos pelo usuário que permitem a aplicação de restrições e validações sobre os valores dos atributos de uma relação, facilitando a garantia de consistência e integridade de dados no seu banco de dados.

A principal utilidade dos domínios é centralizar as constraints para os tipos de dados comuns evitando repetir várias vezes as mesmas restrições, uma para cada tabela e centralizando-as, facilitando a manutenção.

Para criar um domínio, utilizamos:

```SQL
CREATE DOMAIN domain_name AS data_type
    COLLATE collation  --opcional
    DEFAULT expression --opcional
    CONSTRAINT constraint_name constraint_expression
```

A clause `COLLATE` é usada para especificar como o banco de dados executará a ordenação de uma coluna que pertença àquele domínio, enquanto, a clause `DEFAULT`, obviamente, define um valor padrão para aquele datatype e, por fim, a constraint é usada para definir as restrições daquele tipo específico.

A ``constraint_expression`` pode ser `NOT NULL`, simplesmente definindo que aquele tipo não pode ser definido com [[Valores NULL]] ou ser da forma `CHECK (expression)` onde `expression` deve ser uma expressão que retorna um valor booleano e pode referenciar o valor a ser testado usando a variável `VALUE`, o check passará se a expressão retornar `TRUE` ou `UNKNOW`.

Um problema pode ocorrer quando utilizamos a constraint `NOT NULL` no domínio, basicamente, o SQL confia no valores armazenados num determinado datatype como de fato pertencendo àquele datatype, então, por exemplo, a consulta:

```SQL
INSERT INTO table_name (column_name)
    VALUES ((SELECT column_name FROM table_name WHERE false))
```

Nessa query, `SELECT column_name FROM table_name WHERE false` gerará um valor `NULL` mas que é classificado com o mesmo tipo de `column_name`, nesse caso, o `SQL` confia que os dados são de mesmo tipo e insere o valor nulo, mesmo que a constraint de domínio declare `NOT NULL`, por isso, recomenda-se que a constraint de domínio seja usada apenas para restringir o formato dos valores a serem inseridos, deixando o `NOT NULL` como uma constraint de coluna, definida na criação da tabela.

Um exemplo de criação e utilização de domínios seria:

```SQL
CREATE DOMAIN email
	CONSTRAINT CHECK 
	    (VALUE ~ '^[A-Za-z0-9._%+-]+@[A-Za-z0-9.-]+\.[A-Za-z]{2,}$');
	    
CREATE TABLE users (
    username TEXT NOT NULL,
    email email NOT NULL,
    password TEXT NOT NULL
);
```
