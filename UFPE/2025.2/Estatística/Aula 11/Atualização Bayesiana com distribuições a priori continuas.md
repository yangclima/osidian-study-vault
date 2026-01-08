Até agora realizamos o processo de [[Atualização Bayesiana]] apenas em casos em que temos um número finito de hipóteses, podemos pensar que nesses casos nossas hipóteses são [[Variável Aleatória Discreta|v.a.d.'s]], nosso objetivo agora é desenvolver melhor o nosso processo de atualização para lidar com casos que apresentam intervalos finitos de hipóteses, isto é, as hipóteses atuam como [[Variável Aleatória Contínua|variáveis aleatórias continuas]].

Como você já deve esperar, atuaremos da mesma forma que fizemos até aqui para passar de uma abordagem discreta para uma abordagem contínua, ou seja, substituiremos a [[Função massa de probabilidade]] por uma função densidade de probabilidade e os somatórios por [[Integral definida|integrais]].

Para exemplificar a ideia de um intervalo contínuo de hipóteses, imagine que temos uma moeda que será lançada, sabemos que os resultados desse lançamento pode ser modelado por uma variável aleatória discreta $X$ que deve seguir uma [[Distribuição de Bernoulli]], isto é $X \sim \text{Bern}(p)$ porém, o parâmetro $p$ é que será objeto das nossas hipóteses e pode, por sua vez, assumir qualquer valor no intervalo $[0,1]$, assim, a nossa hipótese pode ser pensada como uma v.a.c. distribuída no intervalo $[0,1]$.

Em geral, lidaremos com situações onde teremos uma modelagem para um processo aleatório através de uma distribuição de probabilidade parametrizada para a qual cada possível valor de parâmetro será uma hipótese que costumamos denotar por $\theta$ ou por $\mathcal{H}_\theta$, ou seja, por simplicidade, denotaremos por $\theta$ a "hipótese de que o parâmetro de interesse tenha valor $\theta$".

Na nossa estrutura Bayesiana para lidar com distribuições contínuas teremos a função densidade de probabilidade de hipóteses tanto a priori como a posteriori assim como a verossimilhança.

Por exemplo, lançando uma moeda, a variável aleatória $X$ que retorna $0$ quando o lançamento resulta em cara e $1$ caso contrário deve seguir uma distribuição de Bernoulli de parâmetro $\theta$, ou seja, $X \sim \text{Bern}(\theta)$, podemos então supor que o valor $\theta$ segue uma **distribuição de probabilidade a priori** dada por $f(\theta) = 2\theta$, nossa verossimilhança então seria $p(X=1|\theta) = \theta$ e também $p(X=0|\theta) = 1 - \theta$.

Agora, munidos da [[Lei da probabilidade Total para distribuições contínuas]] podemos construir a nossa tabela de atualização Bayesiana para distribuições contínuas, a diferença chave é que como aqui temos intervalos contínuos teremos apenas uma linha na nossa tabela representando o intervalo no qual $\theta$ está distribuído, para o nosso exemplo acima, temos então, para um resultado de $x = 1$ no primeiro lançamento:

| **Hipótese**         | **Intervalo**          | **Priori**         | **Veros.**     | **Numerador**                                                          | **Posteriori**        |
| -------------------- | ---------------------- | ------------------ | -------------- | ---------------------------------------------------------------------- | --------------------- |
| $\mathcal{H}_\theta$ | $[\theta_-, \theta_+]$ | $f(\theta)d\theta$ | $p(x\|\theta)$ | $p(x\|\theta)f(\theta)d\theta$                                         | $f(\theta\|x)d\theta$ |
| $\theta$             | $[0,1]$                | $2\theta d\theta$  | $\theta$       | $2\theta^2d\theta$                                                     | $3\theta^2d\theta$    |
| **Total**            | $[0,1]$                | $1$                | -              | $\int_{\theta_-}^{\theta_+} p(x\|\theta)f(\theta)d\theta = p(x) = 2/3$ | -                     |

Assim continua válida a nossa interpretação a respeito do teorema de Bayes:

$$
f(\theta| x) = \dfrac{p(x|\theta)f(\theta)d\theta}{\int_{\theta_-}^{\theta_+} p(x|\theta)f(\theta)d\theta} = \dfrac{p(x|\theta)f(\theta)d\theta}{p(x)}
$$
Ou mesmo:

$$
f(\theta| x) \propto {p(x|\theta)f(\theta)d\theta}
$$

Ou ainda, de maneira mais elegante:

$$
\text{Posteriori} \propto \text{Priori}\times\text{Verossimilhança}
$$

Além disso, assim como antes, podemos utilizar os resultados obtidos na primeira atualização para repetir o processo e realizar uma segunda atualização, obtendo, por exemplo, a probabilidade de obter $0$ no segundo lançamento, dado que obtivemos $1$ no primeiro, o que é feito basicamente multiplicando a função densidade de probabilidade a posteriori pela verossimilhança do segundo lançamento, temos então:

| **Hipótese**         | **Intervalo**          | **Priori**         | **Veros.**     | **Numerador**                                                          | **Posteriori**        | Veros.           | **Numerador**                                                        | Posteriori                    |
| -------------------- | ---------------------- | ------------------ | -------------- | ---------------------------------------------------------------------- | --------------------- | ---------------- | -------------------------------------------------------------------- | ----------------------------- |
| $\mathcal{H}_\theta$ | $[\theta_-, \theta_+]$ | $f(\theta)d\theta$ | $p(x\|\theta)$ | $p(x\|\theta)f(\theta)d\theta$                                         | $f(\theta\|x)d\theta$ | $p(x_2\|\theta)$ | $p(x_2\|\theta)p(x\|\theta)f(\theta)d\theta$                         | $f(\theta\|x,x_1)d\theta$     |
| $\theta$             | $[0,1]$                | $2\theta d\theta$  | $\theta$       | $2\theta^2d\theta$                                                     | $3\theta^2d\theta$    | $1 - \theta$     | $3\theta^2(1-\theta)d\theta$                                         | $12\theta^2(1-\theta)d\theta$ |
| **Total**            | $[0,1]$                | $1$                | -              | $\int_{\theta_-}^{\theta_+} p(x\|\theta)f(\theta)d\theta = p(x) = 2/3$ | -                     | -                | $\int_{\theta_-}^{\theta_+} 3\theta^2(1-\theta)d\theta = p(x) = 1/4$ |                               |

Seguindo o mesmo processo, podemos realizar infinitas atualizações Bayesianas sobre uma distribuição a priori inicial e encontrar a probabilidade do parâmetro de interesse dado uma conjunto qualquer de dados.