Uma das principais características do modelo relacional é, de fato, a possibilidade de implementar relações entre tabelas no banco de dados. Essas relações podem ser de três tipos: `One-to-One`, `One-to-Many` e `Many-to-Many` definidas pelas constraints de foreign key das tabelas.

A primeira relação, `One-to-One`, um pra um, é definida quando uma linha tabela precisa referenciar especificamente uma e somente uma linha de outra, por exemplo:

```SQL
CREATE TABLE users (
    id SERIAL PRIMARY KEY,
    username TEXT NOT NULL,
    email TEXT NOT NULL
);

CREATE TABLE profiles (
   social_name TEXT NOT NULL,
   description TEXT NOT NULL,
   user_id INT NOT NULL UNIQUE,
   CONSTRAINT fk_user_id CHECK FOREIGN KEY(user_id) REFERENCES user(id),
)
```

Aqui, como cada `profile` referencia apenas um usuário e existe a constraint `UNIQUE` no seu atributo `user_id`, isto é, não pode haver mais de um `profile`associado ao mesmo usuário, temos uma relação de um pra um.

Um outro caso seria:

```SQL
CREATE TABLE reinbursement_submissions (
   value INTEGER NOT NULL,
   description TEXT NOT NULL,
   type TEXT NOT NULL,
   user_id INT NOT NULL,
   CONSTRAINT fk_user_id CHECK FOREIGN KEY(user_id) REFERENCES user(id),
   CONSTRAINT valid_type CHECK (type IN 'alimentação', 'transporte')
)
```

Aqui, basicamente definimos um relacionamento de um pra muitos, uma submissão de reembolso deve referenciar um e somente um usuário da tabela users mas, pode haver múltiplas submissões para um único usuário.

Por outro lado, um exemplo de relacionamento `Many-to-Many` seria:

```SQL
CREATE TABLE reimbursement_submissions (
    id SERIAL PRIMARY KEY,
    value INTEGER NOT NULL,
    description TEXT NOT NULL
);

CREATE TABLE categories (
    id SERIAL PRIMARY KEY,
    name TEXT NOT NULL
);

CREATE TABLE reimbursement_categories (
    reimbursement_id INT NOT NULL,
    category_id INT NOT NULL,
    CONSTRAINT fk_reimbursement 
        FOREIGN KEY(reimbursement_id) REFERENCES reimbursement_submission(id),
    CONSTRAINT fk_category 
        FOREIGN KEY(category_id) REFERENCES category(id),
    PRIMARY KEY (reimbursement_id, category_id)
);
```

Aqui, quem define esse relacionamento de vários para vários é a tabela intermediária `reimbursement_categories` que permite a associação de várias categorias para várias submissões e vice versa.

