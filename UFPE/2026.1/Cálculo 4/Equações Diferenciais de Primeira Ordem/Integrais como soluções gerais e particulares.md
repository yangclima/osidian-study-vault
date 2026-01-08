As [[Equações Diferenciais]] ordinárias de primeira ordem da forma:

$$
\dfrac{dy}{dx} = f(x,y);
$$

Se torna extremamente simples, caso $f(x,y)$ for independente de $y$, nesse caso, temos:

$$
\dfrac{dy}{dx} = f(x)
$$

Que pode ser facilmente resolvida simplesmente [[Integral Indefinida|inetegrando]] de ambos os lados da equação, obtendo então uma solução do tipo:

$$
y(x) = G(x) + C
$$

Onde $G(x)$ é a antiderivada de $f(x)$ e $C$ é uma constante qualquer, essa solução é chamada então de **solução geral da EDO** já que para cada valor de $C$ existe uma solução particular da equação, fixada então uma condição inicial dada por $f(a) = b$ encontramos o valor de $C$ que nos fornece uma **solução particular da EDO** através de:

$$
b - G(a) = C
$$

Essa simplicidade se estende ainda para equações diferenciais ordinária de segunda ordem da forma:

$$
\dfrac{d^2y}{dx^2} = h(x)
$$

Que podemos resolver através de duas integrações consecutivas, na primeira, obtemos:

$$
\dfrac{dy}{dx} = I(x) + C_1
$$

Onde $I(x)$ é a antiderivada de $h(x)$ e $C_1$ uma constante qualquer, integrando  novamente, obtemos então:

$$
\dfrac{dy}{dx} = J(x) + C_1x + C_2
$$

Onde $J(x)$ é a antiderivada de $I(x)$ e tanto $C_1$ quanto $C_2$ são constantes quaisquer.