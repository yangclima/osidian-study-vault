Como vimos, a [[Esperança]] é uma medida da tendência central de uma [[Variável Aleatória Discreta]], portanto, ela seria uma ótima escolha se quiséssemos representar a nossa v.a. por um valor único, entretanto, essa representação deixaria uma lacuna, uma vez que, apesar de conhecer a nossa tendência central, não sabemos o quão "espalhados" os dados estão em torno dessa tendência, esse é o problema que a **variância e o desvio padrão** resolvem.

Definimos a **variância** como:

$$
\text{Var}(x) = E[(X-\mu)^2]
$$

Onde $\mu = E[X]$. Porém, podemos simplificar isso utilizar as propriedades da esperança, obtendo:

$$
\text{Var}(X) = E[X^2] - E^2[X]
$$

Perceba que a variância é uma média do quadrado das distâncias entre cada valor que pode ser assumido pela v.a. e o valor esperado, ponderado pela probabilidade de cada valor, portanto:

$$
\text{Var}(X) = \sum_{i=1}^{n} p(x_i)\cdot (x_i-\mu)^2
$$

Um problema que aparece, no entanto, é que a unidade da variância é o quadrado da unidade da variável aleatória, portanto, estabelecemos o **desvio padrão** da seguinte maneira:

$$
\sigma = \sqrt{\text{Var}(X)}
$$

A variância possui algumas propriedades:

1. $\text{Var}(X + Y) = \text{Var}(X) + \text{Var}(Y)$
2. $\text{Var}(aX + b) = a^2\text{Var}(X)$

A primeira delas, porém, só é válida se as variáveis $X$ e $Y$ forem [[Independência de Eventos|independentes]] entre si, o que só é verdade se:

$$
P(X=a, Y=b) = P(X=a)\cdot P(Y = a)
$$

E a segunda, só é válida se $a$ e $b$ forem constantes.