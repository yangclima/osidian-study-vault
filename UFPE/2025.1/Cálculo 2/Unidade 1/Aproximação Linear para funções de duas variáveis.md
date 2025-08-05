Assim como em Cálculo 1 usávamos [[Aproximação Linear|Aproximações lineares]] de funções de variável únicas, em Cálculo 2 podemos utilizar o [[Planos Tangentes|Plano Tangente]] para criar uma linearização da função $f(x,y)$ que nos serve de aproximação do valor de $f(x,y)$ quando $(x,y)$ estiver próximo de um dado ponto $(a,b)$, sendo assim, temos:
$$
f(x,y) \approx \dfrac{\partial f}{\partial x}(a,b)\cdot(x - a) + \dfrac{\partial f}{\partial y}(a,b)\cdot(y - b); \ \text{Quando } (x,y) \approx (a,b)
$$
A aproximação será ótima quando $x$ for muito próximo de $a$ e $y$ muito próximo a $b$ mas perde precisão na medida que a distância entre eles aumenta. A única restrição da aproximação linear é que ela não funciona bem quando a função não é continua em $(a,b)$ ou nas suas proximidades.
