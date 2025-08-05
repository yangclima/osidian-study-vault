---
tags:
---
Podemos entender o conceito de limite intuitivamente através de algumas ideias simples, podemos por exemplo, imaginar uma função definida para todos os pontos $x$ tal que $x \neq a$:
![[limite-função.png|center]]
Dessa maneira, quanto mais $x$ se aproxima de $a$, mais $f(x)$ se aproxima de $L$, sendo assim, $L$ é chamado de "**limite de $f(x)$ quando $x$ tende a $a$**" e pode ser denotado por:
$$
L = \lim\limits_{x \rightarrow a} f(x)
$$
Porém, essa definição é muito vaga, sendo assim, podemos definir limite da seguinte forma:
$$
\forall \epsilon > 0, \exists \delta > 0 \ \ \text{tal que} \ \ \forall x \in D_f; 0 < |x-a| < \delta \implies |f(x) - L| < \epsilon 
$$
![[limite-pela-definição.png |center]]
## Propriedades dos limites
- $\lim\limits_{x \rightarrow a} x = a$
- $\lim\limits_{x \rightarrow a} c = c$
- $\lim\limits_{x \rightarrow a} f(x) + \lim\limits_{x \rightarrow a} g(x) = \lim\limits_{x \rightarrow a} f(x) + g(x)$
- $\lim\limits_{x \rightarrow a} f(x) \cdot \lim\limits_{x \rightarrow a} g(x) = \lim\limits_{x \rightarrow a} f(x) \cdot g(x)$
- $\dfrac{\lim\limits_{x \rightarrow a} f(x)}{\lim\limits_{x \rightarrow a} g(x)} = \lim\limits_{x \rightarrow a} \dfrac{f(x)}{g(x)}$

Já sabemos que o limite é um conceito chave para a definição das derivadas, mas além disso, sobre o limite repousa também a definição de [[Função contínua]].