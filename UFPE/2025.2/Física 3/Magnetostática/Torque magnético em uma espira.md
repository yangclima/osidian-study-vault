---
tags:
  - anky
---
Uma espira é basicamente um loop de corrente formado por um por um fio condutor, assim, como já sabemos que existe uma [[Força magnética em um fio]] devido a corrente $I$ que passa nesse fio, considerando uma espira quadrada no plano $xy$ e um campo magnético $\vec B = B\hat{i}$ na direção de $x$

![[fg3_018.png]]

Podemos obter as forças sobre cada um dos segmentos dessa espira como:

$$
\vec F_1 = 0
$$
$$
\vec F_2 = IaB\hat{k}
$$
$$
\vec F_3 = 0
$$
$$
\vec F_4 = -IaB\hat{k}
$$

Logo, a força resultante é nula, há porém um torque resultante $\vec \tau$ dado por:

$$
\vec\tau = IabB\hat j = IAB\hat j
$$

Onde $A$ é a área da espira ($A = ab$). e tomando $\vec A = A\hat n$ podemos definir:

$$
\vec\tau = I\vec A \times \vec B
$$

Para uma $N$-espira (Uma espira composta por $N$ voltas de um fio) temos então:

$$
\vec\tau = NI\vec A\times \vec B = NIAB\sin{\theta}
$$

Onde $\theta$ é o ângulo entre $\vec A$ e $\vec B$ e damos o nome especial de **momento de dipolo magnético** $\vec \mu$  ao termo $\vec\mu = NI\vec A$  e portanto podemos escrever o torque como:

$$
\vec\tau  = \vec\mu \times \vec B
$$

E o trabalho e a energia potencial de um dipolo magnético num campo $B$ é então:

$$
\Delta U = - W = -\mu B (\cos{\theta_1} - \cos{\theta_0})
$$

E por fim, a força magnética em um dipolo é:

$$
\vec F_B = \nabla(\vec\mu\cdot\vec B)
$$