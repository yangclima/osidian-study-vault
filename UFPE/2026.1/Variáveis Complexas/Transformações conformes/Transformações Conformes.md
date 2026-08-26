Seja $f(z) = w$ uma [[Transformações complexas|transformação complexa]] definida em um domínio $D$, ela é dita **Conforme** em  um ponto $z_0$ se preservar o ângulo entre duas curvas $C_1$ e $C_2$ quaisquer que se cruzam em $z_0$.

Esse ângulo entre as curvas no ponto $z_0$, no caso de termos duas curvas suaves, consiste no ângulo $\theta$ entre os seus vetores tangentes no ponto $z_0$ considerando o intervalo $[0,\pi]$, sendo assim, ao mapear essas curvas através de uma transformação conforme, preservamos esse ângulo em magnitude, isto é, tanto para as curvas originais quanto para suas imagens sob a transformação $f$ mantendo o vetor tangente a uma curva inalterado, basta rotacionarmos o outro vetor a um ângulo $\theta$ para que eles coincidam e, além disso, essa rotação, ocorre no mesmo sentido (Horário ou trigonométrico) tanto para as curvas originais quanto para suas imagens, diz-se então que o ângulo entre as curvas se preserva em magnitude e sentido.

Pode-se provar então que:

> Se $f$ for uma [[Funções Complexas|função complexa]] [[Diferenciabilidade e Analiticidade|analítica]] em um domínio $D$ que contém $z_0$ e se $f^\prime(z_0) \neq 0$, então $w = f(z)$ é uma transformação conforme.

Apesar de não surgir diretamente desse teorema, funções analíticas não são conformes em seus pontos críticos (Pontos $z_0$ tais que $f^\prime(z_0) =0$), porém, existe uma propriedade dessas transformações nos seus pontos críticos, chamada de dilatação do ângulo:

> Seja $f$ uma função analítica no ponto $z_0$ e $n$ um inteiro tal que $f^\prime(z_0) = f^{\prime\prime}(z_0) = \cdots = f^{(n-1)}(z_0) = 0$ e $f^n(z_0) \neq 0$ então, o ângulo entre duas curvas suaves quaisquer que passam pelo ponto crítico $z_0$ é aumentado por um fator multiplicativo $n$ por uma transformação complexa $w = f(z)$.

