---
tags:
  - Geometria-Analítica
---
Existem diversas formas de equações para descrever uma reta, mas a ideia principal é sempre a mesma: Descrever algébrica e geometricamente o conjunto de pontos que pertencem a mesma reta, para tal, um dos principais conceitos é o **Coeficiente Angular ($m$)** um escalar que determina a inclinação da reta e é dado por:
$$
m = \dfrac{y-y_0}{x-x_0} = \dfrac{\Delta y}{\Delta x}
$$
- $m$ pode ser calculado a partir de quaisquer dois pontos da reta em questão
- Quando $m$ é positivo isso quer dizer que a variação em $y$ é positiva para uma variação positiva de $x$, ou seja, a reta é **crescente**
- Quando $m$ é negativo isso quer dizer que a variação em $y$ é negativa para uma variação positiva de $x$, ou seja, a reta é **decrescente**
- Quanto maior $|m|$ maior a variação de  $y$ para uma mesma variação de $x$, ou seja, **a inclinação da reta é maior**
- Se duas retas possuem o mesmo coeficiente angular, ou seja $m_1 = m_2$, elas são paralelas
- Se duas retas possuem coeficientes angulares $m_1$ e $m_2$ tal que $m_1m_2 = -1$, as retas são perpendiculares
- Só existe uma reta para cada valor de $m$ que passa por um ponto $x$ qualquer do [[O plano coordenado|plano coordenado]]
Tendo em vista a ideia acima (Só existe uma reta para cada valor de $m$ que passa por um ponto $x$ qualquer do plano coordenado), podemos escrever a equação da reta como:
$$
y - y_0 = m(x - x_0) 
$$
==Esta é a [[Equação ponto-coeficiente angular da reta]]==

Um segundo conceito é o **coeficiente linear ($b$)** um escalar que determina o valor da coordenada $y$ do ponto $(0, y)$ ou  seja, o ponto em que a reta cruza o eixo das ordenadas, só existe uma reta para cada par de coeficiente linear e coeficiente linear, sendo assim, esta é outra maneira de descrever uma reta qualquer:
$$
y = mx + b
$$
==Esta é a [[Equação reduzida da reta]]==

Um problema que pode aparecer é que as equações acima não funcionam para retas verticais, paralelas o eixo $y$ já que o coeficiente angular ($m$) não seria calculável ja que $\Delta y = 0$, para isso, temos a seguinte equação que considera a possibilidade de aplicar o coeficiente angular à variável $y$:
$$
Ax + By + C = 0
$$
==Esta é a [[Equação geral da reta]]==