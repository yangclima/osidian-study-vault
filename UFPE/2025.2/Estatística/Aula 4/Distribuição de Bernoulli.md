A Distribuição de Bernoulli é uma das mais importantes distribuições de probabilidade da estatística, ele modela uma tentativa em um [[Conceitos de Probabilidade|evento]] que resulta invariavelmente em falha ou sucesso, ou seja, uma escolha binária, suas principais características são: 

1. Uma [[Variável Aleatória Discreta]] que segue a distribuição de Bernoulli pode assumir apenas dois valores: $1$ que equivale a um sucesso, ou $0$ que equivale a um fracasso.
2. A probabilidade de sucesso é definida como $P(X = 1) = p$ e a probabilidade de fracasso é definida por $P(X = 0) = 1 - p$, onde $p$ é chamado de parâmetro da distribuição.

Portanto, a [[Função massa de probabilidade]] dessa distribuição é definida como:

$$
p(a) = 
\begin{cases}
p & \text{se } a = 1\\
1 - p & \text{se } a = 0\\
\end{cases}
$$

Se a variável aleatória discreta segue uma distribuição de Bernoulli com um parâmetro $p$, denotamos esse fato por $X \sim \text{Bernoulli}(p)$ ou $X \sim \text{Bern}(p)$ (Lê-se: "$X$ segue uma Distribuição de Bernoulli de parâmetro $p$).

Vários experimentos podem ser modelados usando essa distribuição, por exemplo, num lançamento de um dado, podemos estabelecer uma v.a.d. $X$ que retorna $1$ (Sucesso) caso obtenhamos um $6$ e $0$ (Fracasso) caso o contrário, nesse caso temos que  $X \sim \text{Bern}(1/6)$, dessa maneira, num lançamento a probabilidade de obter um Sucesso é $P(X =1) = p = 1/6$ e  a probabilidade de obter um Fracasso é $P(X = 0) = 1 - p = 5/6$.
