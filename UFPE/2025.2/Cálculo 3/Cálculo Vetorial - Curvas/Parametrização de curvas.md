As curvas mais gerais que podemos desenhar, como por exemplo a vista na seguinte imagem

![[calc3-001.png|center]]

Não podem ser descritas como [[Função|funções]] simples de $x$ ou de $y$, entretanto podemos utilizar de um processo denominado **Parametrização de curvas** para descrever a curva definindo $x$ e $y$ como funções de um determinado parâmetro $t$, ou seja, $x = f(t)$ e $y = g(t)$. O mais comum é que esses parâmetro seja o tempo, fazendo com que a curva descreva, por exemplo, a trajetória de uma partícula.

Essa descrição paramétrica é útil já que através dela podemos aplicar os conceitos que já conhecemos do cálculo diferencial e integral a essa curvas, descobrindo propriedades como [[Cálculo da reta tangente ao gráfico de f(x)|reta tangente]], comprimento de arco, área e muito mais.

Em geral, utilizamos as formas comuns de calcular essas propriedades mas efetuando sobre elas mudanças de variável através da regra da cadeia, pro exemplo, a inclinação da reta tangente:
$$
\dfrac{dy}{dt} = \dfrac{dy}{dx} \dfrac{dx}{dt} \implies \dfrac{dy}{dx} = \dfrac{\dfrac{dy}{dt}}{\dfrac{dx}{dt}}
$$
Para a área sobre a curva temos:
$$
A = \int_\alpha^\beta y\,dx = \int_\alpha^\beta g(t)f^\prime(t)dt 
$$
E para o comprimento de arco, temos:
$$
L = \int_\alpha^\beta \sqrt{1 + \left(\dfrac{dy}{dx}\right)^2}\,dx = \int_\alpha^\beta \sqrt{1 + \left(\dfrac{dy/dt}{dx/dt}\right)^2}\,f^\prime(t)dt 
$$

# Parametrizações clássicas
## Reta e segmento
$$
r(t) = P_0 + \vec{n}t
$$
$$
r(t) = P_0 + (Q_0 - P_0)t\,; \ \ t \in [0,1]
$$

## Circunferência
$$
r(t) = (x_0 + r\cos(t),y_0 + r\sin(t))\,; \ \ t \in [0,2\pi]
$$
## Elipse
$$
r(t) = (x_0 + a\cos(t), y_0 + b\sin(t))\,; \ \ t \in [0,2\pi]
$$

