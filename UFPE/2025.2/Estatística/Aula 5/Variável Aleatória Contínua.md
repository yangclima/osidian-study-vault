Como toda [[Variável Aleatória Discreta|v.a.]], uma variável aleatória contínua associa cada valor do espaço amostral a um número real:

$$
X: \Omega \rightarrow \mathbb{R}
$$

A diferença entre uma v.a.c. e uma v.a.d é então que o "contradomínio" da v.a.d é uma coleção contável de valores enquanto o de uma v.a.c. é um intervalo contínuo, nesse sentido, em questão de cálculo, a mudança é que ao invés de somarmos usando um somatório, usamos uma [[Integral definida|integral]].

**Definição:** Uma variável aleatória é contínua se existe um função $f(x)$ tal que, para qualquer $a \leq b$:

$$
\int_a^b f(x)\,dx = P(a \leq X \leq b)
$$

De maneira análoga a [[Função massa de probabilidade]], $f(x)$ é chamada de **Função Densidade de Probabilidade** (f.d.p.), que satisfaz (Devido a sua relação com a [[Função probabilidade]]):

1. $f(X) \geq 0$
2. $\int_{-\infty}^{\infty} f(X)d\,x = 1$

Perceba entretanto, que $f(x)$ não é propriamente uma função probabilidade, precisamos integrá-la para isso, nesse caso, a restrição $f(x) \leq 1$ não é válida.