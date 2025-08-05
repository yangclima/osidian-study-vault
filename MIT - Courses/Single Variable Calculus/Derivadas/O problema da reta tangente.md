Ao longo da história, muitos matemáticos tentaram definir com perfeição o conceito da reta tangente mas quem de fato o revolveu qualitativamente foi Fermat. Podemos intuitivamente pensar que a reta tangente é aquela que toca o gráfico da função em apenas um ponto, contudo, essa definição é rasa e só funciona para alguns tipos de curva, a solução mais refinada surgiu através do método qualitativo de Fermat e do conceito de limite, da seguinte maneira:

Dada a função $f$ e seu gráfico $y=f(x)$ a reta tangente ao gráfico de $f$ no ponto $P$ é igual ao limite da reta secante ao pontos $P$ e $Q$ - Sendo $Q$ um ponto também pertencente ao gráfico de $f$ e próximo a $P$ - quando $Q$ tente a $P$ ao longo do gráfico de $f$.
![[secante-tende-a-tangente.png]]
## Cálculo do coeficiente angular
Tomando o ponto $P = (x_0, y_0)$ fixado e o ponto $Q=(x, y)$ se aproximando dele, temos que, o coeficiente angular da reta tangente seria dado por $\dfrac{y-y_0}{x-x_0}$, porém, quando $Q$ se aproxima de $P$ os valores de suas coordenadas ficam cada vez mais próximos, dessa forma, se simplesmente igualássemos os dois ponto conseguiríamos algo pouco útil ( $\dfrac{0}{0}$ ), esse problema é resolvido através do conceito de [[Limite]], onde assumimos que as coordenadas se aproximam infinitamente mas nunca serão iguais, em notação, teríamos:
$$
\lim\limits_{Q \rightarrow P} m_{sec} = m_{tg} = \lim\limits_{x \rightarrow x_0} \dfrac{y-y_0}{x-x_0}
$$
Ao se deparar com esse tipo de equação, precisamos encontrar um caminho para sair dessa indeterminação,  caso a nossa função fosse $f(x) = x^2$ poderíamos fazer:
$$
\lim\limits_{x \rightarrow x_0} \dfrac{f(x)-f(x_0)}{x-x_0} = \lim\limits_{x \rightarrow x_0} \dfrac{x^2 - x_0^2}{x - x_0}
$$
E sairíamos da indeterminação apenas com álgebra:
$$
\lim\limits_{x \rightarrow x_0} \dfrac{x^2 - x_0^2}{x - x_0} = \lim\limits_{x \rightarrow x_0} \dfrac{(x - x_0)(x + x_0)}{x - x_0} = \lim\limits_{x \rightarrow x_0} \dfrac{\cancel{(x - x_0)}(x + x_0)}{\cancel{x - x_0}} = \lim\limits_{x \rightarrow x_0} x + x_0
$$
A solução já foi encontrada, já que não há mais problemas em substituir diretamente os valores e o nosso limite resultaria então em $2x_0$, essa seria portanto a inclinação da reta tangente para qualquer ponto $(x_0, y_0)$ dado, desde que esse pertença ao gráfico de $f(x)$, por exemplo, a reta tangente ao gráfico de $y = x^2$ no ponto $P=(2,4)$ teria inclinação $m = 2x_0 = 2 \cdot 2 = 4$ . Ao lidar com limites, soluções e desenvolvimentos algébricos são sempre necessários, nesse sentido, um grande facilitador é a chamada [[Notação Delta]], teríamos então:
$$
\lim\limits_{x \rightarrow x_0} \dfrac{f(x)-f(x_0)}{x-x_0} = m_{tg} = \lim\limits_{\Delta x \rightarrow 0} \dfrac{f(x_0 + \Delta x)-f(x_0)}{\Delta x} 
$$
Nesse momento já chegamos no conceito de [[Derivada]].

> Vale ressaltar que nem toda curva possui uma tangente bem definida em todos os pontos do seu gráfico e para que a tangente exista é importante que seu valo seja o mesmo para um ponto $Q$ se aproximando de $P$ pela direita ou pela esquerda, esse conceito pode ser melhor compreendido através dos [[Limites Laterais]] 
> ![[tangente-indefinida.png]]