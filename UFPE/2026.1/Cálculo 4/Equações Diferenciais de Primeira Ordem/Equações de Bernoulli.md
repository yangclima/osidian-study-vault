Uma [[Equações Diferenciais|Equação diferencial]] da forma:

$$
y\prime +p(x)y = q(x)y^n
$$

Onde $p(x)$ e $q(x)$ são funções contínuas e diferenciáveis e $n$ é um número real, é chamada de **Equação de Bernoulli**.

Inicialmente, notamos que, no caso onde $n=0$ ou $n=1$, essa equação recai no caso de uma [[EDO's Lineares de Primeira Ordem|EDO linear de primeira ordem]] e pode ser resolvida pelo [[Método dos Fatores Integrantes]].

Para qualquer outro valor de $n$, podemos resolver essa equação através de uma substituição de variáveis, onde o primeiro passo é dividir ambos os membros da equação por $y^n$, obtendo:

$$
y^{-n}y\prime + p(x)y^{1-n} = q(x)
$$

Agora, aplicamos a substituição de variáveis com uma variável $v = y^{1-n}$, que derivada implicitamente, já que ambas $v$ e $y$ são funções de $x$, nos dá o seguinte resultado:

$$v^\prime = (1-n)y^{-n}y^\prime \implies \dfrac{v^\prime}{(1-n)} = y^{-n}y^\prime$$

Assim, podemos substituir a variável $y$ na EDO pela variável $v$, obtendo um "nova" equação:

$$
\dfrac{v^\prime}{(1-n)} + p(x)v = q(x) \implies v^\prime + {(1-n)}p(x)v = q(x){(1-n)}
$$

O que agora corresponde a uma EDO Linear de 1ª Ordem em $v$ e pode então ser resolvida em função dessa variável pelos métodos que já conhecemos.

Após resolver então a equação em $v$, substituímos pelo seu equivalente em $y$, obtendo a solução geral da nossa EDO.