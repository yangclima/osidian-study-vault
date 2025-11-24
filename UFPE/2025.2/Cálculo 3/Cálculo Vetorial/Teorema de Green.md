O **Teorema de Green** é um teorema que permite relacionar uma [[Integrais de linha|integral de linha]] sobre uma curva $C$ a uma Integral dupla sobre a região $D$ que tem como fronteira a curva $C$ e enuncia o seguinte:

> Seja uma curva $C$ plana, simples, fechada, contínua por partes, orientada positivamente (Percorrida no sentido anti-horário) e $D$ a região delimitada por $C$, Se $P$ e $Q$ possui [[Derivadas parciais]] de primeira ordem contínuas sobre uma região aberta que contenha $D$, então:
> $$\oint_C Pdx + Qdy = \iint \limits_D \left(\dfrac{\partial Q}{\partial x} - \dfrac{\partial P}{\partial y}\right)dA$$

Este teorema é extremamente útil ao possibilitar que encontrando uma integral dupla sobre $D$ muito complexa, possamos calcular essa integral utilizando uma integral de linha sobre o contorno da região, da mesma forma, encontrando uma integral de linha complexa sobre uma determinada curva fechada $C$, podemos encontrar uma forma mais fácil de calculá-la com uma integral dupla sobre a região $D$ envolvida por ela.

Um outro uso muito importante do **Teorema de Green** é para calcular áreas quando a integral dupla é mais complexa, basicamente, como $A = \iint \limits_D 1\,dA$, procuramos duas funções $P$ e $Q$ que satisfaçam $\dfrac{\partial Q}{\partial x} - \dfrac{\partial P}{\partial y} = 1$, existem vários exemplos ($P=0$ e $Q=x$, $P = -y$ e $Q = 0$, $P = -\dfrac{1}{2}y$ e $Q = \dfrac{1}{2}x$, ...), o que nos dá as seguintes fórmulas para o cálculo de Área:

$$
A = \oint_C xdy = -\oint_C ydx = \oint_C -\dfrac{1}{2}y\,dx + -\dfrac{1}{2}x\,dy
$$

