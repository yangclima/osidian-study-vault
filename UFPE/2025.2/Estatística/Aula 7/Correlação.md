Sofremos com a [[Covariância]] o mesmo problema que sofríamos com a [[Variância e Desvio Padrão|variância]], as unidade, a unidade da covariância de duas [[Variável Aleatória Contínua|variáveis aleatórias]] $X$ e $Y$ é obtida como o produto da unidade de $X$ pela unidade $Y$ o que faz com que apenas mudar a escala dos valores dessas v.a.'s acabe alterando o valor da covariância, o que atrapalha muito ao tentarmos comparar covariâncias, a **correlação** surge então como uma solução para esse problema:

O **coeficiente de correlação** $\rho$ entre duas variáveis aleatórias $X$ e $Y$ que possuem desvio padrão $\sigma_X$ e $\sigma_Y$, respectivamente, é definido como:

$$
\text{Cor}(X,Y) = \rho = \dfrac{\text{Cov}(X,Y)}{\sigma_X\sigma_Y}
$$

E suas propriedades são:

1. $\rho$ é covariância das padronizações de $X$ e de $Y$, ou seja, se você padronizar $X$ e $Y$, v.a's de desvio padrão $\sigma_X$ e $\sigma_Y$, respectivamente, por meio de $Z_X$ e $Z_Y$ tal que ambas tenham desvio padrão $1$ e esperança $0$, então $\text{Cov}(Z_Y,Z_X) = \rho$.
2. $\rho$ é adimensional.
3. $-1 \leq \rho \leq 1$, de tal modo que $\rho$ é $1$, se e somente se, $Y = aX + b$ com $a > 0$ e $\rho$ é $-1$ se e somente se $Y = aX + b$ com $a < 0$, ou seja, $\rho$ mede a relação linear entre $X$ e $Y$.