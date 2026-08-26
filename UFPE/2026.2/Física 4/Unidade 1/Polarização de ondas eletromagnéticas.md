Como sabemos, a luz, como qualquer [[Maxwell e a previsão das Ondas Eletromagnéticas|Ondas eletromagnética]] é uma onda transversal, isto é, uma [[Ondas Eletromagnéticas Planas|onda]] formada por uma [[Campo Elétrico]] e um [[Campo Magnético]] ortogonais entre si e à direção de propagação, contudo, até agora, por simplicidade, lidamos apenas com ondas que são ditas **Linearmente Polarizadas** ou **Planarmente polarizadas**, isto é, ondas ondo a direção do campo magnético não varia no tempo, enquanto, ainda assim, sua magnitude e direção podem mudar (Variam senoidalmente). Nesse caso,  o campo elétrico, chamado aqui de **perturbação óptica**, reside num plano fixo chamado **plano de vibração** que contém simultaneamente $\vec E$ e $\vec k$ (A Direção de propagação).

Imagine agora duas ondas eletromagnéticas planas se propagando na mesma região no espaço, se seus campos elétricos forem colineares podemos dizer que a onda formada pela superposição dessas duas ondas manterá o mesmo plano de vibração mesmo que sua fase possa mudar, porém se seus campos elétricos forem mutuamente perpendiculares a onda resultante pode ou não ter um plano fixo de polarização, sendo, nesse caso, dita, **Não polarizada** e a forma exata (Estado de polarização) que a luz toma aqui depende de vários fatores.

Consideremos duas ondas com campos elétricos perpendiculares (note que considerar apenas $\vec E$ e uma direção de propagação determina completamente o campo magnético $\vec B$):

$$\vec E_x(z,t) = E_{mx}\cos{(kw - \omega t)}\hat i$$
$$\vec E_y(z,t) = E_{my}\cos{(kw - \omega t + \phi)}\hat j$$

Aqui, $\phi$ é a fase relativa entre as duas ondas, perceba que essa diferença de fase faz com que o cosseno na onda $\vec E_y$  só atinja o valor do cosseno da onda $\vec E_x$ após um período de tempo de $\phi/\omega$, de modo que $\vec E_y$ está atrasada com relação a $\vec E_X$. A onda resultante da superposição dessas duas será simplesmente:

$$\vec E(z,t) = \vec E_x(z,t) + \vec E_y(z,t)$$

Um dos principais casos específicos ocorre quando $\phi = 2\pi n; n \in \mathbb{N}$, nesse caso, temos as ondas em fase e a onda resultante dada por:

$$\vec E (z,t) = (E_{mx}\hat i + E_{my}\hat j)\cos{(kz-\omega t)}$$

E como vemos, a onda mantém um caráter polarizado, com o campo elétrico variando senoidalmente numa direção fixa, em outras palavras, temos um plano de polarização fixo, e o Ângulo de inclinação do campo elétrico é dado segundo a relação:

$$\tan{(\theta)} = \frac{E_{my}}{E_{mx}} \implies \theta = \arctan\frac{E_{my}}{E_{mx}}$$

De forma similar, podemos decompor qualquer onda linearmente polarizada em duas componentes, uma na direção $\hat i$  e uma na direção $\hat j$.

Uma condição semelhante ocorre quando as ondas estão defasadas por um ângulo que é um múltiplo ímpar de $\pi$ ($\phi = (2n + 1)\pi; n \in \mathbb{N}$),  nesse caso, a onda continua polarizada, mas temos uma rotação com relação ao caso anterior.

Um outro caso interessante ocorre quando as ondas estão defasadas por qualquer ângulo $\phi$ dado por $\phi = -2\pi/2 + 2\pi n; n\in \mathbb{N}$, e tem mesma magnitude, nesse caso, temos:

$$\vec E(z,t) = E_{m}\cos{(kz-\omega t)}\hat i + \vec E_{m}\cos{(kw -\omega t - \pi/2)}\hat j$$

Mas $\cos(A - \pi/2) = \sin{(A)}$, logo:

$$\vec E(z,t) = E_{m}\cos{(kz-\omega t)}\hat i + E_{m}\sin{(kw -\omega t )}\hat j$$

Nesse caso, a amplitude da onda é dada por:

$$(\vec E \cdot \vec E)^2 = E_m$$

Porém a sua direção varia com o tempo, não temos mais uma onda linearmente polarizada, a direção do vetor do [[Campo Elétrico]] gira no sentido horário (Visto por um observador em direção ao qual a onda se propaga) e dizemos que ela é **Circularmente Polarizada à direita**.

A luz natural geralmente consiste em uma luz não polarizada, por ser gerada, por interações caóticas de átomos e partículas extremamente excitados e por isso seu plano de vibração varia aleatoriamente com o tempo. Apesar disso, podemos representar a luz através de duas ondas planas transversais e defasadas para as quais a fases relativa muda rapidamente com o tempo.