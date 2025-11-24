Um artifício muito útil a respeito das [[Variável Aleatória Discreta|Variáveis aleatórias]] é poder compor novas variáveis aleatórias mais complexas através de operações algébricas entre variáveis aleatórias mais simples.

Por exemplo, representando por $X_j$ a [[Variável Aleatória Discreta]] que resulta $1$ caso o $j-ésimo$ lançamento de uma moeda seja cara e $0$ caso contrário, sabemos então que $X_j$ segue uma [[Distribuição de Bernoulli]] $X_j \sim \text{Bern}(1/2)$, podemos então definir a seguinte v.a.d.:

$$
X = X_1 + X_2 + \cdots + X_n
$$

Nesse caso, $X$ retorna o número de lançamentos que resultaram em cara, e nesse caso, como sabemos, $X$ segue uma [[Distribuição Binomial]] de parâmetros $n$ e $p = 1/2$.

Dessa forma percebemos que podemos operar e compor variáveis aleatórias de maneira a definir outras com maior complexidade, manipulando e alterando, inclusive, sua distribuição.