Como já sabemos, incongruências que Maxwell identificou na [[Lei de Ampére]] o levaram a adicionar um novo termo a equação dessa lei, adicionando um termo relacionado a [[Corrente de deslocamento]] a essa lei chegando na Lei de Ampere-Maxwell completando as chamadas [[Equações de Maxwell]] diferencial são:

| Lei                | Equação                                                                                      |
| ------------------ | -------------------------------------------------------------------------------------------- |
| **Gauss**          | $$\nabla\cdot\vec E = \dfrac{\rho}{\varepsilon_0}$$                                          |
| **Faraday**        | $$\nabla\times\vec E = -\dfrac{\partial \vec B}{\partial t}$$                                |
| **Gauss**          | $$\nabla\cdot\vec B = 0$$                                                                    |
| **Ampére-Maxwell** | $$\nabla\times\vec B = \mu_0\vec J + \mu_0\varepsilon_0\dfrac{\partial \vec E}{\partial t}$$ |
> Curiosidade: Originalmente Maxwell escreveu 20 equações que posteriormente foram sintetizadas por Heaviside e Gibbs em 4 equações para o espaço tridimensional e posteriormente em 2 para o espaço-tempo quadridimensional e apenas 1 usando a álgebra de Clifford ou Álgebra Geométrica.

Entretanto, se analisarmos essas Leis no Vácuo, isto é, sem presença de matéria, teremos:

| Lei                | Equação                                                                       |
| ------------------ | ----------------------------------------------------------------------------- |
| **Gauss**          | $$\nabla\cdot\vec E = 0$$                                                     |
| **Faraday**        | $$\nabla\times\vec E = -\dfrac{\partial \vec B}{\partial t}$$                 |
| **Gauss**          | $$\nabla\cdot\vec B = 0$$                                                     |
| **Ampére-Maxwell** | $$\nabla\times\vec B =\mu_0\varepsilon_0\dfrac{\partial \vec E}{\partial t}$$ |

Aqui, Maxwell identificou uma interessante simetria entre as equações da lei de Ampére e da [[Lei de Faraday]], duas equações acopladas, isto é, o [[Campo Magnético]] interfere no [[Campo Elétrico]] e vice-versa, para resolver esse acoplamento, podemos usar a relação $\nabla \times (\nabla \times A) = \nabla(\nabla \cdot A) - \nabla^2 A$ aplicando a a ambos os lados de ambas as equações, chegando nas relações:

$$\nabla^2\vec E = \mu_0\varepsilon_0 \dfrac{\partial^2\vec E}{\partial t^2}$$
$$\nabla^2\vec B = \mu_0\varepsilon_0 \dfrac{\partial^2\vec B}{\partial t^2}$$


O interessante é que estas são basicamente equações de onda com a velocidade $v =  1/{\sqrt{\mu_0\varepsilon_0}} = 3\times 10^8 \ m/s$.,  de modo que cada componente cartesiana $\vec E$ e $\vec B$ satisfaz uma equação de onda em 3 dimensões.

Intuitivamente podemos pensar que basicamente uma variação temporal de $\vec B$ leva ao surgimento de um campo elétrico $\vec E$ que varia no tempo e que ao variar gera um $\vec B$ que também varia e assim por diante infinitamente e assim  surgem as ondas.

Assim, Maxwell previu a existência de ondas Eletromagnéticas se propagando no vácuo a uma velocidade absurda $c$, um choque para a comunidade científica da época, que acreditava que todas as ondas precisavam de um meio para se propagar, com a posterior comprovação da existência dessas ondas por Hertz, foi inclusive proposta a existência de um meio chamado Éter, que preenchia todo o espaço "vazio" e permitia a propagação das ondas eletromagnéticas, nunca comprovada.

Dado que essas ondas foram provadas experimentalmente depois e se propagam na velocidade da Luz, com a relação anteriormente vista para a sua velocidade, temos que a velocidade da Luz $c$ é:

$$
c = v = \frac{1}{\sqrt{\mu_0\varepsilon_0}} = 3\times 10^8 \ \ m/s
$$

Um fato interessante é que Maxwell dessa forma abalou as estruturas anteriores da física com uma unificação da eletricidade ($\varepsilon_0$ vem da [[Lei de Coulomb]]) e do magnetismo ($\mu_0$ vem da [[UFPE/2026.1/Eletromagnetismo/Magnestostática/Lei de Biot-Savart|Lei de Biot-Savart]]) e da óptica além de posteriormente servir com principal inspiração de Einstein para elaborar a relatividade geral que destronou a aceleração, rainha das leis de Newton e coroou a velocidade da Luz!

A partir daí faz todo o sentido expressar o [[Campo Elétrico]], por exemplo, como uma função senoidal da posição $x$ (Tal qual para [[Ondas sonoras progressivas|Ondas sonoras]]), assumindo $x$ como direção de propagação da onda, e do tempo $t$, como:

$$\vec E = E_m \sin{(kx - wt)}\hat j$$

Onde $E_m$ é a amplitude do campo elétrico, $x$ é a direção de propagação da onda, $k$ é o número de onda e $\omega$ a frequência angular e onde assumimos que o campo elétrico aponta na direção do vetor unitário $\hat j$ o que faz sentido já que, a partir da [[Lei de Gauss]], podemos mostrar, substituindo $\vec E$ por essa função de seno, iremos notar que o campo elétrico precisa ser perpendicular a direção de propagação, adotamos então $\hat j$ por facilidade, além disso, usando a [[Lei de Faraday]] podemos mostrar que o campo magnético deve ser perpendicular a $\vec E$ e à direção de propagação, temos portanto:

$$
\vec B = B_m \sin{(kx-wt)}
$$

Em ambas as relações, vale:

$$k = \frac{2\pi}{\lambda}$$
$$
\omega = \frac{2\pi}{T} = 2\pi f
$$
$$
v = c  = \frac{\omega}{k}
$$

Dizemos então que a onda eletromagnética é uma onda transversal, adotamos, por pura convenção que a direção $\hat i$ é a sua direção de propagação, $\hat j$ é a direção do campo elétrico e $\hat k$ a direção do campo magnético e dizemos que os campos elétrico e magnético estão em fase, de modo que seus máximos e mínimos ocorrem simultaneamente.

Quanto a relação entre essas campos, usando a [[Lei de Ampére]], podemos chegar a relação entre seus módulos:

$$
E_m = cB_m
$$

Ou de forma equivalente:

$$
\vec E = \vec B \times c\hat i \implies \vec B = \dfrac{1}{c}\hat i\times \vec E
$$

Isso não quer dizer, no entanto, que o campo elétrico é mais ou menos intenso que o campo magnético, na realidade, essa comparação não é possível já que os campos não tem unidades equivalente no [[Sistema Internacional de Unidades]].


> **Observação:** Fato notável e que será utilizado posteriormente é que a direção de propagação pode ser escrita como $\vec E \times \vec B$.

