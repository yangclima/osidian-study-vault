Um **Hash** no Redis é uma estrutura de dados de chave valor criada especificamente para guardar **dicionários de objetos**.

Parar criar um ou adicionar campos a um existente:

```bash
hset <chave> <{<campo> <valor>}[]>
```

Para listar os campos de um hash:

```bash
hkeys <chave> 
```

Para listar todos os valores:

```bash
hvals <chave>
```

Para listar todos os campos e valores:

```bash
hgetall <chave>
```

Para verificar se um campo existe:

```bash
hexists <chave> <valor>
```

Para ver o tamanho do hash:

```bash
hlen <chave>
```

Para modificar um campo do hash:

```bash
hmset <chave> <campo> <valor>
```

Para verificar o valor de um campo:

```bash
hmget <chave> <campo>
```

Para incrementar o valor de um campo:

```bash
hincrby <chave> <campo> <incremento>
```

Ou com float:

```bash
hincrbyfloat <chave> <campo> <incremento>
```

Para remover campos:

```bash
hdel <chave> <campo>
```

Para ver o comprimento do valor de um campo:

```bash
hstrlen <chave> <campo>
```

Para adicionar campos somente se estes não estiverem no hash (Sem sobrescrever campo):

```bash
hsetnx <chave> <campo> <valor> 
```