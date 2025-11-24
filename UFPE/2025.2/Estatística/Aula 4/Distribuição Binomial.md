Uma distribuição binomial $\text{Binomial}(n,p)$, ou $\text{Bin}(n,p)$ modela o número de sucessos em $n$ [[Independência de Eventos|tentativas independentes]] onde cada tentativa segue uma [[Distribuição de Bernoulli]] $\text{Bern}(p)$.

Assim, dizemos que uma [[Variável Aleatória Discreta]] $X$ segue uma Distribuição Binomial de parâmetros $n$ e $p$,  ou seja, $X\sim\text{Bin}(n,p)$, se $X$ representa o número de sucessos obtidos em $n$ tentativas de um experimento que segue uma **Distribuição de Bernoulli** com parâmetro $p$, ou seja, a probabilidade de sucesso a cada tentativa é $p$. Nesse caso, $P(X = k)$ é a [[Função massa de probabilidade|probabilidade]] de $k$ das $n$ tentativas resultarem em sucesso e é dada por:

$$
P(X = k) = \binom{n}{k}\cdot p^k \cdot (1-p)^{n-k}
$$
Onde: 
 - $\binom{n}{k}$ é o Coeficiente Binomial e representa o número de formas de escolher $k$ sucessos entre $n$ tentativas (Lembre-se que $\binom{n}{k}$ é uma [[Combinações e Permutações|combinação]] de $n$ termos tomados  a ).
 - $p^k$ é a probabilidade de obter exatamente $k$ sucessos
 - $(1-p)^{n-k}$ é a probabilidade de obter exatamente $n - k$ fracassos

Mais uma vez, vários eventos podem ser modelados seguindo essa distribuição, utilizando o mesmo exemplo que usamos para a Distribuição de Bernoulli, lançando um dado $4$ vezes, e em cada tentativa assumindo sucesso caso obtenhamos um $6$ e fracasso, caso contrário, podemos modelar cada um dos lançamentos como uma Distribuição de Bernoulli de parâmetro $1/6$, estabelecemos então uma variável aleatória discreta $X$ que representa o número de sucessos obtidos dos $4$ lançamentos, nesse caso, dizemos que  $X \sim \text{Bin}(4, 1/6)$, e podemos calcular, por exemplo a probabilidade de obtermos $2$ sucessos como:

$$
P(X = 2) = \binom{4}{2}\cdot \left[\dfrac{1}{6}\right]^2\cdot\left[1 -\dfrac{1}{6}\right]^{4-2} = 0.1157
$$



