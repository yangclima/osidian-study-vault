Para entender as propriedades das ondas eletromagnéticas, considere a existência de uma onda eletromagnética se propagando na direção do eixo $x$ e formada por um [[Campo Elétrico]] uniforme na direção $y$ e um [[Campo Magnético]] uniforme na direção $z$, de tal forma, que todos os pontos de qualquer plano $yz$ tem valores iguais para o campo elétrico e campo magnético e estes campos variam apenas com $x$ e com o tempo $t$, nesse caso:

$$
\vec E(x,t) = E(x,t)\hat j \ \ \ \text{e} \ \ \ \vec B(x,t) = B(x,t)\hat k
$$

Essa onda é um modelo físico idealizado e por seu caráter uniforme em planos é chamada de **Onda Eletromagnética Plana** e de **Transversal** já que os campos são perpendiculares a direção de propagação.

Explorando as [[Equações de Maxwell]] podemos encontrar a relação da magnitude dos campos com suas derivadas como:

$$
\dfrac{\partial \vec E}{\partial x} = - \dfrac{\partial \vec B}{\partial t}
$$ (Através da [[Lei de Faraday]])

Ou seja: Para cada ponto no espaço, um campo magnético que varia no tempo está associado a um campo elétrico que varia no espaço.

$$
-\dfrac{\partial \vec B}{\partial x} = \mu_0 \varepsilon_0\dfrac{\partial \vec E}{\partial t}
$$
(Através da [[Lei de Ampére]][[Corrente de deslocamento|-Maxwell]])

Isto é, Para cada ponto no espaço, um campo elétrico que varia no tempo está associado a um campo magnético que varia no espaço.

Através dessa relação obtida, podemos chegar as seguintes [[Equações Diferenciais]]:

$$
\dfrac{\partial^2 \vec E}{\partial x^2} = \mu_0\varepsilon_0\dfrac{\partial^2 \vec E}{\partial t^2}
$$

E similarmente:

$$
\dfrac{\partial^2 \vec B}{\partial x^2} = \mu_0\varepsilon_0\dfrac{\partial^2 \vec B}{\partial t^2}
$$

De tal maneira que, como a equação geral para uma onda unidimensional é:

$$
\dfrac{\partial^2 \psi}{\partial x^2} = \dfrac{1}{v^2}\dfrac{\partial^2 \psi}{\partial t^2}
$$

Onde $v$ é a velocidade de propagação e $\psi$ é a função de onda, então, tanto $\vec E$ quanto $\vec B$ satisfazem essa equação e se propagam com velocidade (Isto vale apenas para o espaço vazio):

$$
v = c =  \dfrac{1}{\sqrt{\mu_0\varepsilon_0}} = 299.792.458 \ \ m\cdot s^{-1} \approx 3\times10^8 \ \ m\cdot s^{-1}
$$

Uma possível solução para a equação de onda unidimensional para os campos elétricos e magnéticos é:

$$
\vec E(x,t) = E_0\sin{\left(\dfrac{2\pi}{\lambda}(x - ct)\right)}\hat j
$$
$$
\vec B(x,t) = B_0\sin{\left(\dfrac{2\pi}{\lambda}(x - ct)\right)}\hat k
$$

Perceba então que a direção de propagação é dada pelo produto vetorial entre os campo, ou seja,  $\vec E \times \vec B$, além disso, o [[Produto interno]] entre os campos é sempre $0$, isto é, $\vec E \cdot \vec B = 0$.


Onde $\lambda$ é o comprimento de onda, e $E_0$ e $B_0$ são as amplitudes do campo elétrico e magnético respectivamente. Por conveniência e significado físico, chamamos o número $k = {2\pi}/{\lambda}$ de **número de onda** e como a frequência é dada por $f=v/\lambda = c/\lambda$ então a nossa **frequência angular** é $\omega = 2\pi c/\lambda$, nesse caso, podemos escrever:

$$
\vec E(x,t) = E_0\sin{\left(kx - \omega t\right)}\hat j
$$
$$
\vec B(x,t) = B_0\sin{\left(kx - \omega t\right)}\hat k
$$

Definimos também o período de oscilação da onda como $T = 1/f =\lambda/c$. 

Fazendo uma análise a partir das relações que obtivemos através das [[Equações de Maxwell]], podemos, usando as funções que definimos para os campos, encontrar uma relação entre as suas magnitudes:

$$
\dfrac{E_0}{B_0} = \dfrac{E}{B} = \dfrac{\omega}{k} = \dfrac{\lambda}{T} = c
$$

Ou seja, para um instante qualquer, a magnitude dos campos elétrico e magnético obedece a relação:

$$
E = cB
$$
