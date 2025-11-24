Assim como definimos a [[Esperança]] para uma [[Variável Aleatória Discreta]], podemos também fazê-lo para uma [[Variável Aleatória Contínua]] o que, como havíamos citado, consiste basicamente numa substituição do somatório, utilizado para uma v.a.d. por uma integral, definimos então:

$$
E[X] = \int_{-\infty}^\infty x\cdot f(x)\,dx
$$

Onde $f(x)$ é a função densidade de probabilidade, que equivale ao temo $P(X=x)$ utilizado nas variáveis aleatórias discretas.

As propriedades que vimos continuam válidas aqui:

1. $E[X+Y] = E[X] + E[Y]$
2. $E[aX + b] = aE[X] + b$
3. Se $Y$ é uma função $h(X)$ então $E[Y] = E[h(x)] = \int_{-\infty}^\infty h(x)\cdot f_X(x)\,dx$