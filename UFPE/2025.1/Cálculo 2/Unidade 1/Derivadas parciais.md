---
aula: 3
---
Dada uma [[Funções de mais de uma variável|função de duas variáveis]] $f(x,y)$ podemos "transformá-la" m uma [[Função|função de uma única variável]] ao fixarmos o valor de uma das variáveis como constante, dado um $b$ constante, por exemplo, podemos chamar de $g$ a função $f(x, b)$ onde $b$ é constante, assim, a [[Derivada|derivada]] de $g$ equivale ao seguinte [[Limite e Continuidade de funções de mais de uma variável|limite]]:
$$
g^\prime(a) = \lim_{h \rightarrow 0} \dfrac{g(a+h) - g(a)}{h} = f_x(a, b) \lim_{h \rightarrow 0} \dfrac{f(a+h, b) - f(a, b)}{h}
$$
A essa derivada, que toma $y$ como constante e considera a variação de $x$ damos o nome de **derivada parcial de $f$ com relação a $x$**, o mesmo poderia ser feito tomando $x$ como constante e mensurando a variação de $y$, teríamos portanto a **derivada parcial de $f$ com relação a $y$**.
# Notação 
As notações para as derivadas parciais são diversas, portanto, a derivada parcial de $f$ com relação a x poderia ser escrita das seguintes maneiras:
$$
f_x(x, y) = f_x = \dfrac{\partial f}{\partial x} = \dfrac{\partial }{\partial x}f(x,y) = \dfrac{\partial z}{\partial x} = f_1 = D_1 f = D_y f
$$
# Calculando derivadas parciais
O cálculo de uma derivada parcial é simples: Pegamos a função de $f(x,y)$ e calculamos sua derivada assumindo que, por exemplo, $y$ é constante, uma função $xy$ seria então $y$, uma função $x^2y + \ln{(xy)}$ seria então $2xy + \dfrac{y}{xy}$ e por aí vai, é sempre importante ter em mente os [[Métodos de resolução de derivadas]].
# Interpretação das derivadas parciais 
As derivadas parciais podem ser interpretadas de maneira geométrica, elas equivalem a inclinação da reta tangente a uma curva num ponto $P$, assim como nas derivadas de variável única, a diferença é que a curva a qual essa reta é tangente equivale a um corte da superfície formada por $f(x,y)$ pelo plano $y = b$ - No caso da derivada parcial em função de $x$ - Além disso, pode ser interpretada também como a taxa instantânea de variação dessa mesma curva formada pela intersecção da superfície com o plano.
# Generalização para funções de mais de duas variáveis
As regras descritas a respeito das derivadas parciais de duas variáveis podem ser estendidas para funções de mais de duas variáveis, escolhemos a variável que irá variar e fixamos o valor de todas as outras, obtendo:
$$
f_x(a, b, \cdots, z) \lim_{h \rightarrow 0} \dfrac{f(a+h, b, \cdots, z) - g(a, b, \cdots, z)}{h}
$$