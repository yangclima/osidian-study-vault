Um outro caso simples de resolução para [[Equações Diferenciais]] é aa solução das chamadas **Equações diferenciais separáveis** através do método de [[Separação de variáveis]]. Uma equação diferencial separável é uma equação que pode ser escrita na forma:

$$
\dfrac{dy}{dx} = g(x)h(y) = g(x)\dfrac{1}{f(y)}
$$

A sua resolução é simples, basicamente, reescrevemos a equação na forma:

$$
f(y)\dfrac{dy}{dx}dx = g(x)dx
$$

E então [[Integral Indefinida|integramos]] ambos os lados da equação obtendo:

$$
F(y(x)) = G(x) + C
$$

Onde $F(y(x))$ é a antiderivada de $f(y)$, $G(x)$ é a antiderivada de $g(x)$ e $C$ é uma constante qualquer. Entretanto, é comum que esse método forneça soluções **implícitas** para $y$, isto é, funções da forma $k(x,y) = 0$ que podem ou não permitir que $y$ seja escrito de forma explicita em termos de $x$.