Enquanto as [[Listas no Redis|listas]] são ordenadas e permitem duplicatas, temos também os sets no Redis que não possuem nem ordenação nem permitem duplicatas.

Para criar um conjunto adicionando um item a ele, usamos:

```bash
sadd <chave> <valor[]>
```

E para listar os valores:

```bash
smembers <chave>
```

Para ver a quantidade de valores:

```bash
scard <chave>
```

Para verificar a presença de um membro no set:

```bash
sismember <chave> <valor>
```

Para ver a diferença entre dois conjuntos:

```bash
sdiff <chave[]>
```

Para armazenar essa diferença num novo set, usamos:

```bash
sdiffstore <nova chave>  <chave[]>
```

A intersecção entre dois conjuntos, por outro lado:

```bash
sinter <chave[]>
sinterstore <nova chave>  <chave[]>
```

E para a união:

```bash
sunion <chave[]>
sunionstore <nova chave>  <chave[]>
```