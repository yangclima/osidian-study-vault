Os [[Tipos de Dados]] são a forma principal de restringir as informações que serão armazenadas no valor de um atributo, porém as restrições impostas são muito grosseiras, de modo que precisamos de uma outra forma de aplicar restrições mais específicas, por exemplo um range de valores aceitados ou uma relação entre colunas que deve obedecida, essa maneira são as `constraints`.

# Restrições `CHECK`
O tipo mais genérico de constraint são as check constraints, as quais podem ser restrições de coluna ou de tabela (Em geral, uma restrição de coluna pode ser escrita como restrição de tabela, mas o contrário não pode ser feito).

Uma restrição ``CHECK`` de coluna opera no valor de uma coluna e impõe, através de uma expressão booleana uma ou mais condições que devem ser seguidas pelo valor da coluna para que esse valor seja aceito, tentar inserir um dado que não satisfaz as constraints resultará num erro, por exemplo:

```SQL
CREATE TABLE products (
    name TEXT CHECK (name <> ''),
    description TEXT 
        CONSTRAINT not_empty_description CHECK (description <> ''),
    price NUMERIC CHECK (price > 0),
    discount NUMERIC CHECK (discount/100 < 1)
);
```

No exemplo acima, cada campo tem uma restrição de coluna associada, com a sutil diferença de quem o campo `description` tem uma constraint nomeada, é uma boa prática nomear as constraints já que isso melhora a legibilidade das mensagens de erro. O SQL abaixo é totalmente equivalente ao último exemplo:

```SQL
CREATE TABLE products (
    name TEXT,
    description TEXT,
    price NUMERIC,
    discount NUMERIC,
    CONSTRAINT not_empty_description CHECK (description <> ''),
    CHECK (discount/100 < 1),
    CHECK (name <> ''),
    CHECK (price > 0)
);
```

A diferença aqui é que todas as restrições estão definidas como restrições de tabela ao invés de coluna, na prática não há diferença nenhuma entre o funcionamento das constraints de tabela e de coluna de modo que escolher declarar de uma forma ou de outra é questão de gosto, por outro lado, veja o seguinte exemplo:

```SQL
CREATE TABLE products (
    name TEXT,
    description TEXT,
    price NUMERIC,
    discount NUMERIC,
    CONSTRAINT not_empty_description CHECK (description <> ''),
    CHECK (discount/100 < 1),
    CHECK (name <> ''),
    CHECK (price > 0),
    CHECK ((price - (price)*(discount/100)) > 9.99)
);
```

Nesse exemplo, a restrição `CHECK ((price - (price)*(discount/100)) > 9.99)`, que define que o preço após o desconto deve ser de no mínimo ``9.99`` envolve mais uma coluna e portanto não deve ser declarada como restrição de coluna, mas de tabela.

É importante ter em mente que as constraints de check não permitem referência a valores de outras tabelas ou linhas que não aquela que está sendo atualizada ou criada (Para isso outros tipos de constraint podem usadas) e que essa expressão só é avaliada quando tentamos inserir ou atualizar uma linha.

# Restrições `NOT NULL`
A restrição `NOT NUL`, que pode ser escrita como de coluna ou de tabela, mas é normalmente declarada como restrição de coluna e serve basicamente para definirmos que [[Valores NULL]] não podem ser atribuídos a uma coluna, seguindo a seguinte sintaxe:

```SQL
CREATE TABLE products (
    id INTEGER NOT NULL,
    name TEXT CHECK (name IS NOT NULL),
    description TEXT CHECK (description <> '') NOT NULL,
    price NUMERIC NOT NULL CHECK (price > 0)
);
```

Todos os campos desse exemplo estão com uma restrição que impede valores `NULL` de serem atribuído, isso por que `NOT NULL` e `CHECK (column_name IS NOT NULL)` são expressões equivalentes, apesar disso, no PostgreSQL usar `NOT NULL` é mais eficiente, perceba também que essa restrição pode ser usada junto com uma restrição de check e que a ordem não importa.
# Restrição `UNIQUE`
Quando precisamos restringir o valor um atributo de modo que ele seja único na tabela inteira, como para garantir a unicidade de um `id` usamos a restrição `UNIQUE` exemplificada a seguir

```SQL
CREATE TABLE products (
  id INTEGER UNIQUE,
  name TEXT,
  description TEXT,
  price NUMERIC,
  UNIQUE (name, description)
)
```

No exemplo, restringimos a tabela de modo que não haja dois produtos com o mesmo `id` e nem produtos como uma mesma combinação de `name` e `description`, de forma que produtos de mesmo nome são permitidos desde que tenha diferentes descrições.

Um problema que pode surgir é que quando dois valores `NULL` são comparados a comparação retorna sempre que eles são distintos, para contornar isso sem precisar usar a declaração `NOT NULL` usamos `NULL NOT DISTINCT` como a seguir:

```SQL
CREATE TABLE products (
  id INTEGER UNIQUE NULL NOT DISTINCT,
  name TEXT,
  description TEXT,
  price NUMERIC,
  UNIQUE (name, description)
)
```

Assim, imputamos que podem até existir uma linha com `id = NULL`, mas somente uma, já que uma outra linha com null setado nessa coluna violaria a constraint.

# Chaves Primárias
Podemos usar a constraint `PRIMARY KEY` para definir um identificador universal para as linhas da coluna, efeito similar poderia ser feito usando `UNIQUE` , mas não há um limite para o uso dessa última numa tabela, enquanto `PRIMARY KEY` é mais semântica e limitada a um uso por tabela, um exemplo, seria:

```SQL
CREATE TABLE products(
    id INTEGER PRIMARY KEY,
    name TEXT,
    description TEXT
);
```

Nessa caso, `id` será automaticamente marcado como `UNIQUE` e `NOT NULL` e será referenciado por padrão ao criar uma `FOREIGN KEY` sem especificar a coluna. Apesar do PostgreSQL não obrigar, é altamente recomendado que cada tabela tenha uma chave primária.
# Chaves estrangeiras
Chaves estrangeiras são as constraints usadas para definir [[Relações básicas entre tabelas|relações entre tabelas]] mantendo integridade referencial entre elas, por exemplo:

```SQL
CREATE TABLE orders (
    id INTEGER PRIMARY KEY,
    product_id INTEGER REFERENCES products,
    buyer_id INTEGER REFERENCES users (id),
    quantity INTEGER
);
```

Nesse caso, definimos que `product_id` faz referência a tabela `products`, como nenhuma coluna dessa outra tabela foi especificada a referência será feita com base na chave primária de ``products``, da mesma forma `buyer_id` faz referência a tabela `users`, especificamente a coluna `id` dessa tabela, fazendo isto, exigimos que `product_id` (E analogamente `buyer_id`) sejam `NULL` ou iguais a algum valor de `PRIMARY KEY` de alguma linha em `products`. Assim como para as chaves primárias, também podemos definir conjuntos de colunas como chaves estrangeiras:

```SQL
CREATE TABLE certificates (
	id INTEGER PRIMARY KEY,
	name TEXT,
	course TEXT,
	user_id INTEGER,
	FOREIGN KEY (name, course, user_id) REFERENCES users(name, course, id)
)
```

Assim definimos que a combinação dos atributos `name`, `course` e `id` de uma linha de `certificates` deve ser compatível com o conjunto de atributos ``name``, ``course``, ``id`` de uma linha de `users`, para isso a quantidade e tipo das colunas em cada conjunto de atributos deve ser compatíveis.

Em alguns casos muito específicos, podemos criar chaves estrangeiras que fazem referência a própria tabela, por exemplo:

```SQL
CREATE TABLE tree (
    node_id INTEGER PRIMARY KEY,
    parent_id INTEGER REFERENCES tree,
    name TEXT,
);
```

Nesse caso, cada linha de `tree` é um nó e tem uma propriedade `parent_id` que pode ser `NULL` ou fazer referência a um outro nó da tabela, útil para criar uma estrutura em árvore.

Um tópico importante dentro desse contexto de chaves estrangeiras é configurar como deve se comportar uma linha quando a linha a qual ela faz referência é deletada, e para isso temos 3 opções:

1. Deletar o registro junto quando o registro ao qual ele faz referência for deletado
2. Impedir a deleção de um registro caso haja alguma referência a ele
3. No caso do registro referenciado ser excluído, setar o valor da chave estrangeira para `NULL` ou para o valor padrão

Por exemplo:

```SQl
CREATE TABLE orders (
    id INTEGER PRIMARY KEY,
    product_id INTEGER REFERENCES products
        ON DELETE RESTRICT,
    user_id INTEGER REFERENCES users (id)
        ON DELETE CASCADE,
    store_url TEXT REFERENCES e_stores (url) 
        ON DELETE SET NULL,
    quantity INTEGER
);
```

Nesse caso, se tentarmos excluir um item de `products` enquanto existir uma referência válida a ele, a operação será impedida, por outro lado se excluirmos um registro de `users` enquanto existirem itens de `orders` fazendo referência a ele todos serão excluídos em cascata, por fim, se deletarmos um item de `e_stores` enquanto houver uma referência válida a ele em `orders` a operação será permitida e o valor do atributo `store_url` será setado para `NULL`, poderíamos, por outro lado, usar `ON DELETE SET DEFAULT` para ao invés de setar para `NULL` setar para o valor padrão.

As mesmas restrições podem ser aplicadas com `ON UPDATE` para determinar o comportamento quando um registro referenciado for atualizado.
# Restrição `EXCLUDE`
A constraint `EXCLUDE` é um recurso avançado do PostgreSQL que funciona como uma generalização do `UNIQUE` mas especifica como os dados devem ser comparados para garantir unicidade determinando uma expressão que caso avaliada como `true` impede a criação ou atualização da linha, útil quando tivermos dados complexos que não podem ser comparados simplesmente usando um operador "=", por exemplo:

```SQL
CREATE TABLE appointments (
    room_id INTEGER PRIMARY KEY,
    appointment_time TSRANGE,
    EXCLUDE USING gist (room_id WITH =, appointment_time WITH &&),
);
```

Basicamente, definimos nesse exemplo que, para criar uma nova linha ou atualizar uma antiga, usando o `GiST` (Generalized Search Three), um algoritmo de busca do PostgreSQL para dados multidimensionais como intervalos de tempo, devemos comparar as colunas `room_id` com o operador = e `appointment_time` com o operador `&&`.

