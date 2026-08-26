Para definir uma string na CLI do Redis, usamos pares chave valor:

```bash
set <chave> <valor>
```

E para acessar o valor definido, usamos:

```bash
get <chave>
```

Para acessar parcialmente esse valor, podemos usar:

```bash
getrange <chave> <inicio> <fim>
```

Para definir vários pares ao mesmo tempo usamos:

```bash
mset <chave0> <valor0> [...] <chaveN> <valorN> 
```

Para obter várias chaves ao mesmo tempo, usamos:

```bash
mget <chave0> [...] <chaveN>
```

Para obter o número de caracteres de uma string:

```bash
strlen <chave
```

Se criarmos uma variável numérica com, por exemplo, `set count 0` podemos incrementá-la em uma unidade usando:

```bash
incr <chave>
```

Ou em um número específico de unidades:

```bash
incr <chave> <incremento>
```

Para decrementar:

```bash
decr <chave>

decrby <chave> <decremento>
```

É possível também usar valores float usando `set pi 3.14`, por exemplo e somar/subtrair valores a eles usando:

```bash
incrbyfloat <chave> <incremento>

decrbyfloat <chave> <decremento>
```

Para expirar um valor (Muito usado em [[Caching]]) usamos o comando:

```bash
expire <chave> <tempo em segundos para expirar>
```

E acessar a duração restante usando:

```bash
ttl <chave>
```

Para adicionar uma variável com um tempo de expiração definido usamos:

```bash
setex <chave> <segundos> <valor>
```