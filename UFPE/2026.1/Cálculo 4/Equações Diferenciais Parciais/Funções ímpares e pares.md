Durante a aplicação das fórmulas de Euler-Fourier para encontrar os coeficientes da [[Séries de Fourier|Série de Fourier]] de uma determinada função $f$ é de extrema utilidade saber se a função $f$ em questão é par ou ímpar, sendo que :

- $f$ é ímpar $\iff \forall x \in \mathbb{R}: f(-x) = -f(x)$ 
- $f$ é par $\iff \forall x \in \mathbb{R}: f(-x) = f(x)$ 

Além disso, podemos levar como verdade, relações a respeito do produto de duas funções tal que:

1. $par + par = par$
2. $impar + impar = impar$
3. $impar + par \neq impar$ e $impar + par \neq par$
4. $par \times par = par$
5. $impar\times par = impar$
6. $impar\times impar = par$

Levando então em conta as fórmulas de Euler-Fourier:

1. Se $f$ for ímpar: $a_n = 0$ e $b_n = \dfrac{2}{L}\int_0^Lf(x)\sin(\dfrac{n\pi x}{L})dx$
2. Se $f$ for par: $a_n = \dfrac{2}{L}\int_0^Lf(x)\cos(\dfrac{n\pi x}{L})dx$ e $b_n = 0$

Uma última observação, que costuma ser confundida pelos estudantes é:

- Apesar da série de Fourier $S_f$ ser igual a função $f$ nos seus pontos de continuidade, não necessariamente ela é diferente de $f$ onde ela é descontínua.