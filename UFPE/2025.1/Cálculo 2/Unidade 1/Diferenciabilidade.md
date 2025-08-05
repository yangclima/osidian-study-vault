---
aula: 4
---
Tanto o [[Teorema de Clairaut-Schwarz]] quando a [[Aproximação Linear para funções de duas variáveis]] só funciona bem quando a [[Funções de mais de uma variável|função]] $f(x,y)$ é [[Limite e Continuidade de funções de mais de uma variável|contínua]], nesse sentido assim como no cálculo de variável única, podemos definir uma relação entre diferenciabilidade de uma função e sua continuidade, no caso, a diferenciabilidade de $f(x,y)$ num ponto $(a,b)$ implica sua continuidade, essa diferenciabilidade pode ser definida pela validade do seguinte limite:
$$
\lim_{(x,y) \rightarrow (a,b)} \dfrac{f(x,y) - f(a,b) - \dfrac{\partial f}{\partial x}(a,b)\cdot(x - a) - \dfrac{\partial f}{\partial y}(a,b)\cdot(y - b)}{\sqrt{(x-a)^2 + (y - b)²}} = 0
$$
O limite acima pode ser interpretado como uma aproximação pelo plano tangente no numerador sendo comparado com a distância real entre os pontos $(x,y)$ e $(a,b)$.
