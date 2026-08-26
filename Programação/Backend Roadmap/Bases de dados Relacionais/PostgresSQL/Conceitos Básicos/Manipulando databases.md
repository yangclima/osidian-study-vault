Cada instância de servidor PostgreSQL manipula uma ou mais databases, fazendo das databases o maior nível hierárquico na organização de objetos no SQL. Para criar uma database usamos a operação restrita:

```SQL
CREATE DATABASE database_name
```

O role atual se torna automaticamente o owner da database criada possuindo então o privilégio de removê-la posteriormente. 

A primeira database é automaticamente criada quando a instância Postgres é inicializada no `initdb` e chama-se, por padrão, `postgres` de modo que para criar a primeira database própria precisamos conectar nessa database padrão. 

Além da database `postgres` a inicialização cria também `template1` e `template0` que funcionam de fato como template, cada database criada usando o comando `CREATE DATABASE`  será um clone de `template1`, o qual pode ser modificado e portanto funciona como um default value para as novas databases, `template0`, por outro lado, funciona como um backup padrão da `template1`, e pode ser referenciado quando precisarmos criar uma database "crua" usando:

```SQL
CREATE DATABASE database_name TEMPLATE template0
```

Na prática, qualquer database pode ser usada como template para a criação de outra, mas existem restrições e essa prática não é recomendada.

Para criar uma database para um role específico podemos usar:

```SQL
CREATE DATABASE database_name OWNER owner_name
```

Para alterar uma configuração de uma database seguimos a sintaxe:

```SQL
ALTER DATABASE database_name SET config_name TO new_config_value;
```

Por fim, usamos o seguinte comando para destruir uma database:

```SQL
DROP DATABASE database_name;
```