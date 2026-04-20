A utilidade é uma forma de descrever as [[Preferências]] do consumidor e comparar diferentes cestas de consumo de tal modo que dizer que a utilidade de uma cesta $X$ é maior que de uma cesta $Y$ equivale a dizer que $X \succ Y$ e de modo que a utilidade serve para rotular as curvas de indiferença, entretanto o valor numérico da utilidade é irrelevante e o que importa de fato é a comparação entre a utilidade de duas cestas distintas.

A **função utilidade** é definida então como a função $u(x_1,x_2)$ que atribui a cada cesta $(x_1,x_2)$ um número, denominado utilidade, essa função, no entanto, não é única uma vez que qualquer função que preserve a ordem das cestas é valida da mesma maneira, por isso, podemos, por exemplo, multiplicar uma função utilidade por um fator positivo constante e mesmo assim continuar com uma função utilidade válida, o mesmo ocorrer para qualquer transformação que preserve a ordem das utilidades, transformações desse tipo são denominadas **transformações monotônicas**

Sendo assim, podemos então traçar as curvas de indiferença utilizando o conceito de **curvas de nível**, igualando a função utilidade a um valor constante $c$ e avaliando, encontrando assim a curva de indiferença onde todas as cestas tem a mesma utilidade $c$.

Além disso, podemos pensar nos formatos das curvas de utilidade para os casos mais comuns que, inclusive, já tratamos ao estudar as preferências do consumidor.

# Substitutos perfeitos
Como você deve lembrar, bens ditos **substitutos perfeitos** são aqueles para os quais os consumidores aceitam substituir um pelo outro a uma taxa constante, importando então, apenas o número de itens no casos de substitutos perfeitos que se trocam a uma taxa de um pra um ou o "valor" da cesta no caso em que eles se trocam a uma taxa diferente disso, assim, a função utilidade para bens que são substitutos perfeitos é:

$$u(x_1,x_2) = ax_1 + bx_2$$

Onde $a$ e $b$ são constantes que representam o valor do item $x_1$ e do item $x_2$ para o consumidor, se, por exemplo, o item $1$ vale duas vezes mais que o item $2$ para o consumidor, podemos por exemplo, escolher $a = 2$ e $b = 1$.

# Complementares perfeitos
Como os bens complementares perfeitos são aqueles que os consumidores desejam consumir sempre em proporções fixas, o consumidor é indiferente a cestas que tenham uma quantidade maior de um item que transpassa a proporção, por exemplo, para um consumidor, tanto faz uma cesta de consumo com $1$ pé direito e $1$ pé esquerdo de um sapato, ou uma cesta com $1$ pé direito e $20$ pé esquerdo, nesse exemplo a proporção fixa que o cliente deseja é uma pra um, mas pode variar com a situação. Assim, a nossa função utilidade é:

$$u(x_1,x_2) = \min\{ax_1, bx_2\}$$

Onde as constantes $a$ e $b$ são usadas para exibir a proporção fixa que o consumidor deseja entre os bens, se por exemplo, o item $x_1$ são xícaras de café e o item $x_2$ são colheres de açúcar e o consumidor deseja consumir os produtos na proporção de 2 colheres de açúcar por xícara de café então colocamos $b = 1$ e $a = 2$ (Sim, isso parece estranho, temos a sensação de que estão invertidos, mas de fato é assim que funciona).

# Preferências Quase lineares
Um tipo muito interessante e fácil de se trabalhar, apesar de não ser muito realística são as chamadas **preferências quase lineares**, cuja função utilidade é dada por:

$$
u(x_1, x_2) = v(x_1) + x_2
$$

Onde $v$ é uma função qualquer, assim, qualquer curva de indiferença terá sempre o mesmo perfil, apenas deslocado de acordo com o valor da constante que define.

# Preferências Cobb-Douglas
Uma outra função de utilidade muito usada é a chamada função de utilidade **Cobb-Douglas**, dada por:

$$u(x_1,x_2) = x_1^cx_2^d$$

em que **$c$** e $d$ são números positivos que descrevem as preferências do consumidor. A grande importância dessa função utilidade é que ele tem a expressão algébrica mais simples possível para curvas de indiferença bem comportadas.

# Utilidade Marginal
A utilidade marginal $UM$ é uma taxa de variação que nos indica como a utilidade $U$ de uma cesta de bens $(x_1,x_2)$ varia quando adicionamos uma quantidade $\Delta x$ de um dos itens, de forma que temos a utilidade marginal do item $x_1$, $UM_1$, e a utilidade marginal do item $x_2$, $UM_2$, definidas como:

$$UM_1 = \frac{\Delta U}{\Delta x_1} = \dfrac{u(x_1 + \Delta x_1, x_2) - u(x_1,x_2)}{\Delta x_1}$$

$$UM_2 = \frac{\Delta U}{\Delta x_2} = \dfrac{u(x_1 , x_2+ \Delta x_2) - u(x_1,x_2)}{\Delta x_2}$$

Onde, dessa forma, podemos calcular a variação na utilidade causada por uma pequena variação na quantidade de um bem como:

$$\Delta U = UM\Delta x$$

Note, no entanto que a grandeza da utilidade marginal depende da grandeza da utilidade e portanto da função utilidade específica utilizada, e como vimos, o valor numérico da utilidade de uma cesta por si próprio não tem significado comportamental, entretanto, podemos mesmo assim usar a utilidade marginal para calcular algo que possui significado comportamental: A Taxa Marginal de Substituição, valendo a seguinte relação:

$$TMS = \dfrac{\Delta x_2}{\Delta x_1} = - \dfrac{UM_1}{UM_2}$$

Esse sinal negativo da $TMS$ no entanto é irrelevante na maioria das situações e por conveniência podemos tomar a $TMS$ como seu valor absoluto.