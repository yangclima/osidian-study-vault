Um cluster PostgreSQL possui uma ou mais databases, roles e outros objetos compartilhados no cluster inteiro de modo que que cada cliente de conexão estabelecido no servidor pode acessar dados numa única database especificada na requisição de conexão, além disso, é possível configurar o acesso de cada role a cada database e os roles são universais dentro de um cluster.

Cada database contém um ou mais esquemas, que são como diretórios e que, por sua vez, contém [[Noções básicas sobre tabelas|tabelas]] e outros objetos como como [[Tipos de Dados|tipos de dados]], funções e operadores, todos compartilhando o mesmo naming space, o que significa que dentro de um schema, não podem existir dois objetos com mesmo nome, independente do tipo. Esses schemas não são rigidamente separados como as databases, o que implica que os usuários podem acessar qualquer schema numa database na qual estão conectados.

Existem múltiplas razões para usar schemas, como por exemplo permitir que múltiplos usuários usem a database sem interferir um com o outro, organizar a database em grupos lógicos e permitir que aplicações de terceiros atuem na database sem gerar conflitos.

# Criando um Schema
Para criar um Schema, usamos o comando:

```SQL
CREATE SCHEMA schema_name
```

A partir daí, criamos, [[Modificando Tabelas|modificamos]] e interagimos com tabelas nesse esquema usando a referência:

```SQL
schema_name.table_name
```

Objetos e tabelas criados sem especificar o schema são criados num schema padrão da database, chamado `public`.

Para criar uma schema especificamente para um usuário, usamos:

```SQL
CREATE SCHEMA schema_name AUTHORIZATION user_name
```

Uma restrição ao nome de schemas é que eles não podem começar com `pg_`, um prefixo reservado pelo sistema.

# Schema Search Path
Para facilitar a execução de comandos e não obrigar o usuário a constantemente inserir o nome do schema ao acessar uma tabela temos o chamado `Schema Search Path`, basicamente cada usuário tem definido um caminho de pesquisa de modo que ao referenciar um objeto sem especificar o schema o PostgreSQL automaticamente direciona a requisição para um esquema presente nesse caminho buscando sequencialmente por uma compatibilidade, esquema a esquema, além disso, o primeiro schema desse caminho, chamado de ``current schema`` é onde serão automaticamente criados os objetos quando não especificarmos o schema de destino.

Para visualizarmos esse search path usamos:

```SQL
SHOW search_path
```

E para modificá-lo;

```SQL
SET search_path TO current_schema,schema_2,...,public
```


