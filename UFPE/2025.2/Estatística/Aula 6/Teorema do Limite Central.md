Para complementar a intuição que já desenvolvemos precisamente através da [[Lei dos Grandes números]], utilizamos o chamado Teorema do Limite Central para nos fornecer mais algumas informações sobre os valores que muitas amostragens independentes de uma mesma quantidade podem nos fornecer com relação a [[Esperança]], [[Variância e Desvio Padrão]].

Suponha $X_1,X_2, X_3,\cdots, X_n$ [[Variável Aleatória Contínua|variáveis aleatórias]] independentes e igualmente distribuídas, cada uma com uma [[Esperança]] $\mu$ e um [[Variância e Desvio Padrão|desvio padrão]] $\sigma$. Para cada número de amostras $n$, tomamos $S_n$ como a soma dessas variáveis aleatórias e $\overline X_n$ como a média das mesmas, ou seja:

$$
S_n = X_1 + X_2 + X_3 + \cdots + X_n =\sum_{i=1}^n X_i
$$
$$
S_n = \dfrac{X_1 + X_2 + X_3 + \cdots + X_n}{n} =\dfrac{1}{n}\sum_{i=1}^n X_i = \dfrac{S_n}{n}
$$

Nesse caso, utilizando as propriedades da esperança e da variância, podemos obter:


| Medida                      | $S_n$                  | $\overline X_n$   |
| --------------------------- | ---------------------- | ----------------- |
| Esperança ($E[X]$)          | $n\cdot \mu$           | $\mu$             |
| Variância ($\text{Var}[X]$) | $n \cdot \sigma^2$     | $\sigma^2/n$      |
| Desvio padrão ($\sigma$)    | $\sqrt{n}\cdot \sigma$ | $\sigma/\sqrt{n}$ |

Como $S_n$ e $\overline X_n$ são múltiplos, tem a mesma [[Padronização da Distribuição Normal|padronização]], ou seja:

$$
Z = \dfrac{X - \mu}{\sigma}= \dfrac{S_n - n\cdot \mu}{\sqrt{n}\cdot \sigma} = \dfrac{\overline X_n - \mu}{\sigma/\sqrt{n}}
$$

Assim, o Teorema do Limite Central diz que, para $n$ grande:

1. $\overline X_n \approx N(\mu, \sigma^2/n)$
2. $S_n \approx N(n\cdot\mu, n\cdot\sigma^2)$
3. $Z_n \approx N(0,1)$

Ou seja:

1. Para $n$ suficientemente grande, $\overline X_n$ segue aproximadamente uma [[Distribuição Normal]] com mesma [[Esperança]] que $X$ mas com uma menor variância
2. Para $n$ suficientemente grande, $S_n$ segue aproximadamente uma [[Distribuição Normal]] com [[Esperança]] $n$ vezes maior que a esperança de $X$ e com variância também $n$ vezes maior que a variância de $X$
3. A [[Padronização da Distribuição Normal]] de $\overline X_n$ e $S_n$ é a mesma e quando $n$ é suficientemente grande, esta se aproxima de uma distribuição normal padrão.
