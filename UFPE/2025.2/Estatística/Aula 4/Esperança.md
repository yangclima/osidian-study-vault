O valor esperado, média ou esperança de uma [[Variável Aleatória Discreta]] que assume valores $X_1, X_2, X_3, \cdots, X_n$ de probabilidades $p(X_1), p(X_2), \cdots, p(X_n)$ é definido como:

$$
E[X] = \sum_{i=1}^n X_i \cdot p(X_i)
$$

Essa fórmula nos dá o **valor médio esperado** em uma **sequência de experimentos independentes**. Em outras palavras, se fizermos o experimento que gera a variável aleatória $X$ muitas vezes, o valor esperado é o número que **esperamos obter** como a média das observações, nesse sentido, a esperança é uma **medida da tendência central** dos dados.

Um fato importante é que a esperança $E[X]$ pode ser considerado um [[Transformações lineares|operador linear]], portanto valem as seguintes propriedades:

1. $E[X+Y] = E[X] + E[Y]$
2. $E[aX + b] = aE[X] + b$

Além disso, pela definição dada, podemos utilizar:

$$
E[h(X)] = \sum_{i=1}^n h(X_i) \cdot p(X_i)
$$

Podemos utilizar as definições acima para chegar em algumas esperanças para distribuições que conhecemos, veja:

| Distribuição                  | $E[X]$           |
| ----------------------------- | ---------------- |
| [[Distribuição de Bernoulli]] | $p$              |
| [[Distribuição Binomial]]     | $np$             |
| [[Distribuição Geométrica]]   | $\dfrac{1-p}{p}$ |
