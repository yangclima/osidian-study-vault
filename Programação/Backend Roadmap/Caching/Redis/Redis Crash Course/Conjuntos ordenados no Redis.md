Conjuntos ordenados no Redis são conjuntos semelhantes aos [[Conjuntos no Redis|conjuntos normais]] mas com algumas outras funcionalidades, neles, cada valor está associado com um score usado para ordenar o conjunto.

Para adicionar um set ordenado usamos:

```bash
zadd <chave> <{<score> + <valor>}[]>
```

E para listar os valores:

```bash
zrange <chave> <inicio> <fim> [withscores?]

# Para ver todos o valores
zrange <chave> 0 -1
```

Para ver a quantidade de membros:

```bash
zcard <chave>
```

Para ver a quantidade de membros numa parcela da classificação:

```bash
zcount <chave> <score min> <score max>

# Para ver o total
zcount <chave> -inf +inf
```

Para remover um valor:

```bash
zrem <chave> <valor>
```

Para ver a classificação na ordem inversa (ordem decrescente de pontuação), usamos:

```bash
zrevrange <chave> <inicio> <fim> [WITHSCORES?]
```

Para ver o score de um valor:

```bash
zscore <chave> <valor>
```

Para filtrar o conjuntos por uma faixa de scores na ordem inversa, usamos:

```bash
zrevrangebyscores <chave> <max> <min> [WITHSCORES?]
```

Para incrementar o score de um valor:

```bash
zincrby <chave> <valor> <incremento>
```

Para remover valores com base nos scores usamos:

```bash
zremrangebyscore <chave> <min> <max>
```

E para remover com base nas posições:

```bash
zremrangebyrank <chave> <start> <stop>
```