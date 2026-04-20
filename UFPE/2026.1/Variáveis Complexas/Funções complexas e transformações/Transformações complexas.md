Ao trabalhar com [[Funções]], uma ferramenta muito útil é o gráfico da função. 

> Se $y = f(x)$, e $f$ for uma função de uma variável real $x$, o gráfico de $f$ é o conjunto de todos os pontos $(x, f(x))$.

No entanto, ao trabalhar com [[Funções Complexas]], por exemplo $w = f(z)$ tanto o ponto $z$ quanto $w$, sua imagem sob $f$, residem no plano complexo de maneira que $(z, f(z))$ reside no espaço quadridimensional e não é possível desenhar o gráfico dessa função. 

Introduzimos então o conceito de **transformação complexa** para designar a correspondência entre os pontos em um plano $z$ e suas imagens em um plano $w$, correspondência essa especificada pela relação $w = f(z)$.

Dessa maneira, se um ponto $z_0$ no plano $z$ corresponder a um ponto $w_0$ no plano $w$, isto é, $w_0 = f(z_0)$ dizemos que $f$ **mapeia** ou **transforma** $z_0$ em $w_0$ .

Dessa forma, se $w = f(z)$ for uma transformação complexa e $S$ for [[Conjuntos de pontos no plano complexo|conjunto de pontos no plano complexo]] $z$ denominamos o conjunto das imagens dos pontos de $S$ sob $f$ por **imagem de $S$ sob $f$** e denotamos esse conjunto por $S^\prime$, além disso, caso $S$ tiver propriedades especiais e for um domínio $D$ ou curva $C$, podemos também usar $D^\prime$ ou $C^\prime$.

Para a maioria das funções, um entendimento da transformação ocorre apenas após examinar as imagens de diversos conjuntos, num processo que pode ser muito facilitado pelo uso das chamadas **[[Parametrização de curvas|equações paramétricas]]**.

Uma curva paramétrica pode ser considerada como residindo no plano complexo se admitirmos que $x$ e $y$ representam, respectivamente, as partes real e imaginária de um ponto no plano complexo, ou seja, sem $x$ e $y$ forem ambos funções de um parâmetro $t$, isto é, se $x = x(t)$ e $y=y(t)$ com $a \leq t \leq b$, for uma parametrização de uma curva $C$ no plano cartesiano, a equação 

$$z(t) = x(t) + iy(t)$$

É uma **equação paramétrica** dessa curva no plano complexo, **curva paramétrica** ou  **curva paramétrica complexa**, de modo que essa função é denominada **parametrização de $C$**.

Algumas curvas paramétricas complexas mais frequentes são:

> **Reta:** 
> A parametrização de uma reta que passa pelos pontos $z_0$ e $z_1$ é:
> $$z(t) = z_0(1-t) + z_1t\,; \ \ -\infty < t < \infty $$
> Reduzindo o intervalo de variação do parâmetro podemos descrever um segmento de reta entre esses pontos como:
> $$ z(t) = z_0(1-t) + z_1t\,; \ \ 0 \leq t \leq 1 $$
> Ou mesmo um raio que começa em $z_0$ e passa por $z_1$ como sendo
> $$z(t) = z_0(1-t) + z_1t\,; \ \ 0 \leq t \leq \infty$$

> **Circunferência:** 
> A parametrização de uma circunferência de centro em $z_0$e raio $r$ é dada por $$z(t) = z_0 + r(\cos t + i\sin t)\,; \ \ 0 \leq t \leq 2\pi$$Ou, em notação exponencial, usando da [[Forma polar de números Complexos]]
> 
> $$z(t) = z_0 + re^{it}\,; \ \ 0 \leq t \leq 2\pi $$
> 
> de forma similar, variando os limites do intervalo ao qual  o parâmetro $t$ pertence, podemos parametrizar qualquer arco de circunferência.

Uma das principais utilidades das parametrizações é justamente no estudo das transformações complexas, já que se $w = f(z)$ é uma transformação complexa e se $C$ for uma curva parametrizada por $z(t)$ com  $a \leq t \leq b$ então

$$w(t) = f(z(t))\,; \ \ a \leq t \leq b$$

É um parametrização de $C^\prime$ de $C$ sob $w = f(z)$.