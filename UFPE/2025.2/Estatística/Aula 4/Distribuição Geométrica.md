A distribuição Geométrica, modela o número de fracassos antes do primeiro sucesso num sistema onde cada tentativa pode ser modelada como uma [[Distribuição de Bernoulli]], ou seja, se a [[Variável Aleatória Discreta]] $X$ segue uma distribuição geométrica de parâmetro $p$ (Denotamos por $X\sim \text{Geo}(p)$), então a [[Função massa de probabilidade]] $p(k) = P(X = k)$ representa a [[Conceitos de Probabilidade|probabilidade]] de obtermos exatamente $k$ fracassos antes do primeiro sucesso.

Nesse caso, noção função massa de probabilidade é dada por:

$$
p(k) = P(X = k) = (1 -p)^k\cdot p
$$
Onde:
- $(1 - p)$ é a probabilidade de fracasso
- $p$ é a probabilidade de sucesso
- $k$ é o número de fracassos antes do sucesso.

Seguindo o mesmo exemplo que usamos para as outras distribuições, no lançamento de um dado, assumindo a obtenção de um $6$ como um sucesso e a obtenção de qualquer outro valor como um fracasso, podemos modelar cada tentativa como uma Bernoulli de parâmetro $1/6$, nesse caso, estabelecemos uma variável aleatória discreta $X$ que retorna a quantidade de fracassos antes do primeiro sucesso, sabemos então que $X\sim \text{Geo}(1/6)$ e portanto, a probabilidade de obter exatamente $5$ fracassos antes do primeiro sucesso é:

$$
p(5) = P(X = 5) = \left(1 - \dfrac{1}{6}\right)^5 \cdot \dfrac{1}{6} = 0.0669
$$

