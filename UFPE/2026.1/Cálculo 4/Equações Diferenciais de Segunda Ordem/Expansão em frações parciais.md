Ao utilizar a [[Transformada de Laplace]] para [[Solução de EDO's usando Transformada de Laplace|Resolver EDO's]] o grande problema é encontrar a transformada inversa de uma função, nesse sentido, é muito importante dividir as funções $F(s)$ em frações que sejam quocientes simples de polinômios para que possamos aplicar a linearidade da transformada e encontrar mais facilmente a a inversa.

Nesse sentido, o método da **Expansão em Frações Parciais**, muito usado em [[Single Variable Calculus|Cálculo 1]] é amplamente aplicado. O método consiste em expressar uma função $f(x)$ da forma

$$f(x) = \dfrac{P(x)}{Q(x)} = \dfrac{a_0 + a_1x^1 +\cdots + a_{n-1}x^{n-1}+a_nx^n}{b_0 + b_1x^1 +\cdots + b_{n-1}x^{n-1}+b_nx^n}$$

onde $Q(x)\neq0$ através de uma soma de termos fracionários mais simples, o que é possível desde que o grau de $P(x)$ seja menor que o de $Q(x)$, caso em que denominamos $f(x)$ como função **própria**.

Existem 3 casos principais dessa expansão:

# 1º CASO
Se o denominador $Q(x)$ é um produto de fatores lineares distintos, ou seja

$$Q(x)= (a_1x+ b_1)(a_2x + b_2)\cdots(a_kx+b_k)$$

Onde nenhum dos fatores se repete, nesse caso, expandimos $f(x)$ em uma soma:

$$f(x) = \dfrac{A_1}{a_1x+ b_1} + \dfrac{A_2}{a_2x+ b_2} + \cdots + \dfrac{A_k}{a_kx+ b_k}$$

Onde os coeficientes $A_n$ podem ser determinados através de um [[Sistemas lineares|Sistema linear]] obtido multiplicando os dois lados da equação acima pelo produto dos denominadores das frações parciais.

# 2º CASO
Se o denominador $Q(x)$ é um produto de fatores lineares repetidos, ou seja:

$$Q(x) = (a_1x+b_1)^{r_1}(a_2x+b_2)^{r_2}\cdots(a_kx+b_k)^{r_k}$$

Então cada fator linear $k$ repetido deve ser expandido individualmente em:

$$\dfrac{A_1}{a_kx+b_k} + \dfrac{A_2}{(a_kx+b_k)^2} + \dfrac{A_k}{(a_kx+b_k)^{r_k}}$$

Após expandir todos os fatores podemos encontrar os coeficientes $A_n$ multiplicando ambos da equação pelo $MMC$ dos denominadores das frações parciais, isto é, o produto do denominador de maior grau de cada fator e montando um sistema linear.

# 3º CASO
Se o denominador $Q(x)$ é um produto que envolve termos quadráticos irredutíveis, dos quais nenhum se repete, isto é, termos quadráticos da forma $ax^2+ bx + c$ que não possuem raízes reais $(b^2-4ac < 0)$.

Cada um desses fatores quadráticos devem ser expandidos em:

$$\dfrac{A_1x+ A_2}{ax^2+bx+c}$$

Os coeficientes $A_n$ podem então ser encontrado multiplicando ambos os lados da equação pelo $MMC$ dos denominadores e construindo a partir daí um sistema linear.

# 4º CASO
Se o denominador $Q(x)$ é um produto de termos quadráticos irredutíveis mas que se repetem, então cada fator $(ax^2+bx+c)^m$ deve ser expandido como

$$\dfrac{A_1x+ B_1}{ax^2+bx + c} + \dfrac{A_2x+ B_2}{(ax^2+bx + c)^2} + \cdots + \dfrac{A_mx+ A_m}{(ax^2+bx + c)^m}$$

Os coeficientes, mais uma vez, serão obtidos multiplicando ambos os lados da equação pelo $MMC$ dos denominadores das frações parciais e montar o sistema linear.

# 5º CASO
No caso em que o grau de $P(x)$ seja maior que o de $Q(x)$ deve ser adicionar uma etapa anterior a fatoração que consiste na divisão de polinômios visando obter um quociente de polinômios que seja uma função própria.