Enquanto a [[Distribuição Binomial]] modela um sistema onde cada tentativa pode ser modelada por uma [[Distribuição de Bernoulli]] e as tentativas são [[Independência de Eventos|independentes]] entre si, na distribuição Hipergeométrica apesar de cada tentativa poder ser modelada individualmente por uma Bernoulli, elas não são independentes entre si e o resultado de uma, portanto, influencia nos próximos resultados.

Sendo mais específico, a Distribuição Hipergeométrica modela a probabilidade de obter $k$ sucessos em $n$ sorteios **SEM REPOSIÇÃO** de um população de tamanho $N$ que contém $K$ objetos desejáveis, numa situação como essa, estabelecemos uma [[Variável Aleatória Discreta]] $X$ que retorna o número de  sucessos obtidos nas $n$ tentativas e $X\sim \text{Hipergeom}(N,K,n)$ definimos então a [[Função massa de probabilidade]] de $X$ como sendo:

$$
p(k) = P(X = k) = \dfrac{\binom{K}{k}\cdot \binom{N-K}{n-k}}{\binom{N}{n}}
$$


Um bom exemplo de experimento que segue essa distribuição é a realização de $4$ sorteios consecutivos, sem reposição, em uma urna contento $3$ bolas azuis e $5$ vermelhas, estabelecemos uma variável aleatória discreta $X$ que retorna a quantidade de bolas azuis (Nosso sucesso) sorteadas nesses $3$ sorteios, nesse caso, $X \sim \text{Hipergeom}(8,3,4)$, e portanto a probabilidade de obter $3$ sucessos (Sortear $3$ bolas azuis nos $4$ sorteios realizados) é dada por:

$$
p(3) = P(X = 3) = \dfrac{\binom{3}{3}\cdot \binom{8-3}{4-3}}{\binom{8}{4}} = 0,7142
$$
