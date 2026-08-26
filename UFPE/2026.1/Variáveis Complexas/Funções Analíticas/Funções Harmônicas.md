A denominada equação de Laplace é uma das mais importantes da matemática e é muito utilizada no estudo das [[Funções|funções]] potenciais, que já vimos algumas vezes ao tratar de [[Campos escalares e vetoriais]], sobretudo no [[Cálculo 3]] e algumas aplicações da física e do eletromagnetismo.

Essa equação é uma [[Equações Diferenciais|equação diferencial]] parcial de segunda ordem definida como:

$$\nabla^2\phi = \dfrac{\partial^2\phi}{\partial x^2} + \dfrac{\partial^2\phi}{\partial y^2} = 0$$

Soma essa que pode também ser chamada de **Laplaciano de $\phi$**.

Chamamos então de **Função harmônica** no domínio $D$ uma [[Funções de mais de uma variável|função]] $\phi$ de duas variáveis reais $x$ e $y$ que possui [[Derivadas Parciais de ordem superior|derivadas parciais de segunda ordem]] contínuas nesse domínio e satisfaz a equação de Laplace.

E temos o seguinte teorema:

> Seja $f(z) = u(x,y) + iv(x,y)$ uma [[Funções Complexas|função complexa]] [[Diferenciabilidade e Analiticidade|analítica]] em um domínio $D$, então ambas as funções $u$ e $v$ são ditas harmônicas em $D$

Além disso, digamos que $u(x,y)$ é uma função real que é harmônica em um [[Conjuntos de pontos no plano complexo|Domínio]] $D$, nesse caso, se for possível encontrar uma função $v(x,y)$ de modo que $u$ e $v$ satisfazem as [[Equações de Cauchy-Riemann]] em todo o domínio $D$, dizemos que esta função $v$ é a **conjugada harmônica** de $u$ e combinando-as na forma $f(z) = u(x,y) + iv(x,y)$ obtemos uma função complexa analítica neste domínio.