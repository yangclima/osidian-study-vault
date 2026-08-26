Quando temos como entrada de uma rede linear um função periódica e variável, a [[Potencial elétrico|tensão]] e [[Corrente]] produzidas nessa rede, em regime permanente, periódicas (De mesmo período $T$) e variáveis no tempo, temos uma [[Potência|potência]] instantânea

$$p = vi$$

Que também varia no tempo e é periódica, mas com um período $T_p$ diferente, mas que obedece

$$T = nT_p; \ \ \ n=1,2,3,4\cdots$$

De forma similar, a potência média, pode ser definida como:

$$P = \dfrac{1}{T}\int_{t_0}^{t_0 + T}p(t)dt$$

De forma geral, podemos obter essa potência média como:

$$P = \dfrac{1}{2}|\mathbf I||\mathbf V|\cos(\text{ang } V - \text{ang I})$$

O que, num dipolo de tensão de amplitude $V_m$, corrente de amplitude $I_m$ e ângulo $\theta$ da impedância, equivale a:

$$P =\dfrac{V_mI_m}{2} \cos(\theta)$$

Ou, de forma equivalente:

$$P = \dfrac{1}{2}I_m^2\text{ Re}(z)$$

Segue-se daí que:

1. Se $\theta = 0$ o bipolo equivale a um resistor
2. Se $\theta = \pi/2$ o bipolo equivale a um indutor
3. Se $\theta = -\pi/2$ o bipolo equivale a um capacitor
4. Se $\theta \in (0,\pi/2)$ o bipolo equivale a um [[Circuitos RL| Circuito RL]]
5. Se $\theta \in (-\pi/2,0)$ o bipolo equivale a um [[Circuitos RC| Circuito RC]]
6. Se $|\theta| > \pi/2$ o circuito é um elemento ativo