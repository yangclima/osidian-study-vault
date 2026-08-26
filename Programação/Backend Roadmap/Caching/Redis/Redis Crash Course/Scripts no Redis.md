O Redis suporta a execução de script Lua para facilitar performar ações mais complexas no servidor. Esses scripts podem ser executados através do comando `eval`, por exemplo:

```bash
eval "redis.call('set', KEYS[1], ARGV[1])" 1 <chave> <valor>
```

Aqui `KEYS[1]` acessa a primeira chave passada como argumento do comando e `ARGV[1]` o primeiro valor passado como argumento, enquanto `1` diz a quantidade de pares chave valor serão passados.

Esse comando cria uma [[Strings no Redis|string]] e é basicamente é equivalente a:

```bash
set <chave> <valor>
```

Um outro exemplo é:

```bash
eval "local order = redis.call('zrange', KEYS[1], 0, -1); local order = redis.call('zrange', KEYS[1], 0, -1);" 2 <zset> <hset>
```

Também podemos salvar nosso scripts usando:

```bash
script load <script> 
```

Isso retornará uma chave aleatória que será usada para executar o script:

```bash
evalsha <chave aleatória> <n de args> <arg[]>
```

E para cerificar se um script existe:

```bash
script exists <chave aleatório>
```