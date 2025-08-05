Em cálculo 1, definimos a [[Métodos de resolução de derivadas#Derivada de função composta|regra da cadeia]] para funções de uma única variável, o mesmo pode ser feito para [[Funções de mais de uma variável]], de tal forma que isso pode ocorrer de uma forma diferente para cada um dos 2 casos a seguir:
# Caso 1
Seja $f(x,y)$ uma função diferenciável de $x$ e $y$ onde ambas as variáveis podem ser definidas como funções de variável única, ou seja, $x = g(t)$ e $y = h(t)$ temos portanto a função como $f(x(t),y(t))$, que pode ser então diferenciada em função de $t$:
$$
\dfrac{df}{dt} = \dfrac{\partial f}{\partial x}\cdot\dfrac{dx}{dt} + \dfrac{\partial f}{\partial y}\cdot\dfrac{dy}{dt}
$$
# Caso 2
Seja $f(x,y)$ uma função diferenciável de $x$ e $y$ onde $x = g(s,t)$ e $y = h(s,t)$ e portanto a função pode ser descrita como $f(x(s,t),y(s,t))$ temos as derivadas de $f$ como:
$$
\dfrac{\partial f}{\partial t} = \dfrac{\partial f}{\partial x}\cdot\dfrac{\partial x}{\partial t} + \dfrac{\partial f}{\partial y}\cdot\dfrac{\partial y}{\partial t}
$$
$$
\dfrac{\partial f}{\partial s} = \dfrac{\partial f}{\partial x}\cdot\dfrac{\partial x}{\partial s} + \dfrac{\partial f}{\partial y}\cdot\dfrac{\partial y}{\partial s}
$$
# Caso geral
De forma geral podemos definir, para uma função $f$ com número de variáveis igual a $n$:
$$
\dfrac{\partial f}{\partial t_i} = \sum_{k=1}^n \dfrac{\partial f}{\partial x_k}\cdot\dfrac{\partial x_k}{\partial t_i}
$$
