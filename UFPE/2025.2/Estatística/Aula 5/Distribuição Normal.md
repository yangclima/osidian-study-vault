A mais importante distribuição de probabilidade da estatística é de longe a Distribuição Normal, também conhecida como Distribuição Gaussiana, já que esta modela [[Variável Aleatória Contínua|variáveis aleatórias contínuas]] que representam uma infinidade de fenômenos naturais e, além disso, em grande parte dos casos, em grande conjuntos de dados, começa-se a observar uma tendência a seguir uma Distribuição Gaussiana. Essa Distribuição é definida para toda a reta numérica, ou seja, para o intervalo $(-\infty,\infty)$ e tem a seguinte ficha técnica:

| **Característica**                                                                                         | **Valor**                                                                                                                                                                                            |
| ---------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Intervalo                                                                                                  | $(\infty,\infty)$                                                                                                                                                                                    |
| Parâmetros                                                                                                 | $\mu$ (A [[Esperança]] de $X$), $\sigma$ (A [[Variância e Desvio Padrão\|Desvio Padrão]] de $X$)                                                                                                     |
| Função densidade de probabilidade                                                                          | $f(x) = \dfrac{e^{-(x-\mu)^2/2\sigma^2}}{\sqrt{2\pi}}$                                                                                                                                               |
| [[Função de distribuição acumulada para variáveis aleatórias contínuas\|função de distribuição acumulada]] | A função de  distribuição acumulada de $X$ não está definida algebricamente para uma distribuição Normal, para encontrar valor para $F(x)$ fazemos então o uso de tabelas os procedimentos numéricos |
| Notação                                                                                                    | $X\sim \text{Normal}(\mu, \sigma^2)$ ou $X\sim \text{N}(\mu, \sigma^2)$                                                                                                                              |
| Modelo                                                                                                     | Modela a grande maioria dos fenômenos naturais.                                                                                                                                                      |

Note que os parâmetros  da distribuição Normal são, $\sigma$, o desvio padrão da variável aleatória e $\mu$, a [[Esperança]] da  variável aleatória e seu gráfico é sempre centrado em $\mu$ e tem formato de sino.

Uma caso específico muito especial é a chamada Distribuição Normal Padrão, caso onde $Z$, variável aleatória reservada para essa função, segue uma distribuição normal $N(0,1)$, ou seja, $Z\sim N(0,1)$, nesse caso específico, temos:

$$
f(x) = \phi(z) = \dfrac{e^{-z^2/2}}{\sqrt{2\pi}}
$$

Alguns valores interessantes para a aproximação são no caso de uma Distribuição Normal Padrão, são: $P(-1 \leq z \leq 1) \approx 0.68$, $P(-2 \leq z \leq 2) \approx 0.95$ e $P(-3 \leq z \leq 3) \approx 0.99$.

