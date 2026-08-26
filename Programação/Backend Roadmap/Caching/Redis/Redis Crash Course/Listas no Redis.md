Para obter todas as chaves já adicionadas, usamos o comando:

```bash
keys <pattern regex>
```

Para remover **todas as chaves** de todos os bancos de dados configurados de uma vez, zerando os dados, usamos:

```bash
flushall
```

Para definir uma lista ou adicionar valores no fim dela:

```bash
lpush <chave> <valores[]>
```

Para acessar os valores de uma lista:

```bash
lrange <chave> <inicio> <fim>

# Para acessar todos os valores
lrange <chave> 0 -1
```

Para adicionar valores no início da lista:

```bash
rpush <chave> <valores[]>
```

Para ver o comprimento de uma lista:

```bash
llen <chave>
```

Para remover elementos:

```bash
# Remove o último valor da lista retornando-o
lpop <chave>

# Remove o primeiro valor da lista retornando-o
rpop <chave>
```

Para mudar um valor:

```bash
lset <chave> <index> <novo valor>
```

Para setar um valor em uma posição específica:

```bash
linsert <chave> BEFORE|AFTER <valor de ref> <valor>
```

Para acessar o valor a partir do índice:

```bash
lindex <chave> <index>
```

Para adicionar só se a lista já existir, usamos:

```bash
lpushx <chave> <valor>
rpushx <chave> <valor>
```

Para ordenar uma lista:

```bash
sort <chave> <desc?> [Opção de Ordenação]
```

O seguinte comando serve ao mesmo objetivo que o `lpop` mas aceita como argumento um tempo de timeout, basicamente o cliente fica esperando até o fim do timeout por uma resposta no caso da lista não existir, caso a lista seja criada dentro do intervalo de timeout o `lpop` será executado:

```bash
blpop <chave[]> timeout

brpop <chave[]> timeout
```