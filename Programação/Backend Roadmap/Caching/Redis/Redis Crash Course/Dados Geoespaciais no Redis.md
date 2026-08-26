O Redis também oferece amplo suporte a dados Geoespaciais, manipulados usando os seguintes comandos:

Para adicionar um dado:

```bash
geoadd <chave> <{<lat> <long> <tag>}[]>
```

Para acessar as tags (Nomes das cidades, bairros, etc) usamos:

```bash
zrange <chave> 0 -1
```

Para acessar um valor:

```bash
geopos <chave> <tag> 
```

Para ver a distância entre dois lugares:

```bash
geodist <chave> <tag1> <tag2> <unidade>
```

Para ver as localizações registradas que estão num determinado raio com relação a um ponto, usamos:

```bash
georadius <chave> <lat> <long> <raio> <unidade> [WITHCOORD?] [WITHDIST?] [WITHHASH?]
```

Ou:

```bash
georadiusbymember <chave> <tag> <raio> <unidade> [WITHCOORD?] [WITHDIST?] [WITHHASH?] [ASC|DESC?]
```