Agora que sabemos como calcular a probabilidade numa [[Distribuição conjunta]] de [[Variável Aleatória Contínua|variáveis aleatórias]] e como extrair valores individuais dessas variáveis com a [[Distribuição marginal]] queremos então buscar métodos que nos permitam de fato avaliar a relação entre as distribuições das variáveis, o primeiro desses métodos é a **covariância**.

A **covariância** é uma medida do quanto duas variáveis aleatórias variam juntas, pro exemplo, dadas duas variáveis aleatórias $X$ e $Y$, se $X$ cresce quando $Y$ cresce, a covariância de $X$ e $Y$, $\text{Cov}(X,Y)$, deve ser positiva, se quando $X$ cresce, $Y$ diminui, ela deve ser negativa.

Sejam $X$ e $Y$ duas variáveis aleatórias com [[Esperança|médias]] $\mu_X$ e $\mu_Y$ respectivamente. A **covariância de $X$ e $Y$** é definida como:

$$
\text{Cov}(X,Y) = E[(X-\mu_X)(Y-\mu_Y)]
$$

As propriedades da covariância são (Note a relação entre a covariância e a [[Variância e Desvio Padrão|variância]]):

1. $\text{Cov}(aX + b,cX + d) = ac\text{Cov}(X,Y)$
2. $\text{Cov}(X_1+X_2, Y) = \text{Cov}(X_1, Y) + \text{Cov}(X_2, Y)$
3. $\text{Cov}(X, X) = \text{Var}(X)$
4. $\text{Cov}(X, Y) = E[XY] - \mu_X\mu_Y$
5. $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y) + \text{Cov}(X, Y)$
6. Se $X$ e $Y$ são [[Independência de variáveis aleatórias|independentes]], então $\text{Cov}(X, Y) = 0$, porém, a recíproca não é verdadeira, ou seja, $\text{Cov}(P, Q) = 0$ não implica que $P$ e $Q$ são independentes.

Podemos também calcular através de somatórios e integrais a covariância de duas variáveis aleatórias:

No caso de $X$ e $Y$ serem [[Variável Aleatória Discreta|variáveis aleatórias discretas]], temos:

$$
\text{Cov}(X, Y) = \left(\sum_{i=1}^n\sum_{j=1}^mp(x_i,y_i)x_iy_i\right) - \mu_X\mu_Y
$$

No caso de $X$ e $Y$ serem [[Variável Aleatória Contínua|variáveis aleatórias contínuas]], temos:

$$
\text{Cov}(X, Y) = \left(\int_c^d\int_a^bxyf(x,y)dxdy\right) - \mu_X\mu_Y
$$

