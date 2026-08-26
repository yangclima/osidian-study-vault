Para tratar [[Função|funções]] que possuem saltos através da [[Transformada de Laplace]] é útil definir uma função conhecida como **Função Degrau Unitário** ou **Função de Heaviside**, denotada por $u_c$ e definida como:

$$u_c(t)=\begin{cases}0; \ \  \text{para } \ \ t<c \\ 1; \ \  \text{para } \ \ t\geq c\end{cases}$$

De forma similar podemos definir um degrau negativo

$$1-u_c(t)=\begin{cases}1; \ \  \text{para } \ \ t<c \\0; \ \  \text{para } \ \ t\geq c\end{cases}$$

Isso é muito útil para que possamos escrever partidas, por exemplo, uma função que é uma reta de inclinação $t$ entre $\pi$ e $2\pi$  e zero no restante da reta real pode ser descrita usando a função degrau unitário como:

$$f(t) = t(u_\pi(t)-u_{2\pi}(t))$$

A transformada de Laplace dessa função de Heaviside para $c> 0$ pode ser calculada facilmente, obtendo:

$$\mathcal{L}\{u_c(t)\}(s)= \dfrac{e^{-cs}}{s}$$

Muitas vezes iremos considerar, para uma dada função $f$, uma função relacionada $g(t)$ definida por:

$$g(t) = \begin{cases}0; \ t < c \\ f(t-c); t \ge c\end{cases}$$

Que representa basicamente uma translação da função $f$ por uma constante $c$ no sentido positivo de $t$, podemos escrever essa função de forma equivalente como sendo:

$$g(t) = u_c(t)f(t-c)$$

É essa função que dá a enorme importância da função degrau unitário ao tratar da transformada de Laplace, já que, podemos definir como verdadeira a seguinte relação:

> Se a transformada de Laplace de uma função $f$ para $s>a\ge0$ e $c$ for uma constante positiva, vale que 
> $$\mathcal{L}\{u_c(t)f(t-c)\} = e^{-cs}\mathcal{L}\{f(t)\}$$
> De modo recíproco:
> 
> $$u_c(t)f(t-c) = \mathcal{L}^{-1}\{e^{-cs}\mathcal{L}\{f(t)\}\}$$

Podemos, de forma similar encontrar que:

> Se uma função $f$ admite transformada de Laplace para $s > a > 0$ e $c$ for uma constante qualquer:
> $$\mathcal{L}\{e^{ct}f(t)\} = \mathcal{L}\{f(t)\}(s-c)$$
> Ou, de modo inverso:
> $$e^{ct}f(t)=\mathcal{L}\{F(s-c)\}$$

