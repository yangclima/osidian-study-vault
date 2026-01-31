Vimos que a [[UFPE/2025.2/Física 3/Magnetostática/Lei de Ampére]] define que a [[Integrais de linha|integral de linha]] do campo magnético sob uma curva fechada arbitrária é proporcional ao [[Corrente|fluxo de carga]] passando através de uma superfície delimitada por essa curva por uma constante de proporcionalidade $\mu_0$, ou seja:

$$
\oint\vec B\cdot d\vec s = \mu_0I_{env}
$$

Da mesma maneira, vimos que a [[Lei de Faraday]] estabelece que um [[Campo Magnético]] que varia no tempo tem a ele associado um [[Campo Elétrico]] não conservativo cuja integral de linha é igual a [[Derivada]] temporal do [[Fluxo magnético]], isto é:

$$
\oint\vec E \cdot d\vec s = -\dfrac{d\Phi_B}{dt}
$$

Algo que pode vir a mente é que talvez pudesse haver alguma simetria entre o campo magnético e o campo elétrico, isto é, se um campo magnético que varia no tempo tem um campo elétrico associado, poderia um campo elétrico variável temporalmente ter a ele associado um campo magnético? 

De fato essa simetria existe e isso trás a tona alguns problemas relacionados a versão atual que conhecemos da Lei de Ampére, veja:


![[fg3_024.png|center]]


Imagine um [[Capacitores|capacitor]] de placas paralelas, como na imagem acima, onde cada placa está conectada a um fio com corrente $I$, aplicando a lei de Ampére com uma curva amperiana circular em volta do fio do capacitor, escolhendo como superfície a superfície $S_1$ da imagem, iremos obter:

$$
\oint\vec B\cdot d\vec s = \mu_0I
$$


Porém, escolhendo a superfície $S_2$, como $I_{env} = 0$ então, teríamos: 

$$
\oint\vec B\cdot d\vec s = 0
$$

Perceba que há então uma ambiguidade na nossa versão atual da Lei de Ampére, essa ambiguidade foi corrigida por Maxwell e com essa correção veio também a simetria entre os campos magnéticos e elétricos.

Maxwell demonstrou que na verdade, temos que:

$$
\oint\vec B\cdot d\vec s = \mu_0I  + \mu_0\varepsilon_0\dfrac{d\Phi_E}{dt}
$$

Onde $\varepsilon_0\dfrac{d\Phi_E}{dt}$ é chamada de **Corrente de Deslocamento**, no caso do capacitor, podemos checar que essa adição corrige a Lei de Ampére, já que:

$$
\Phi_E = \dfrac{Q}{\varepsilon_0} \implies \dfrac{d\Phi_E}{dt} = \dfrac{1}{\varepsilon_0}\dfrac{dQ}{dt} = \dfrac{I}{\varepsilon_0}
$$

Então, para a superfície $S_2$, temos:

$$
\oint\vec B\cdot d\vec s = \mu_0I
$$

E agora, independente da existência de campos elétricos que variam no tempo, a Lei de Ampére, agora chamada de Lei de Ampére-Maxwell funciona corretamente, e pode ser escrita como:

$$
\oint\vec B\cdot d\vec s = \mu_0(I_{env} + I_d)
$$

Onde $I_d$ é a corrente de deslocamento.