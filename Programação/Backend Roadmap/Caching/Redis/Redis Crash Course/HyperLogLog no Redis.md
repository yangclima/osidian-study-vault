HyperLogLog é um algoritmo probabilístico usado para contar a quantidade de itens únicos num conjunto massivo de valores, estimando esse valor usando pouquíssima memória, sacrificando a precisão exata em troca de extrema velocidade e eficiência.

Para adicionar elementos usamos:

```bash
pfadd <chave> <valor[]>
```

Para contar a quantidade de valores:

```bash
pfcount <chave[]>
```

Para mesclar vários HyperLogLog, usamos:

```
pfmerge <nova chave> <chave[]> 
```