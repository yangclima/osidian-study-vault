Até agora só consideramos [[EDO's Lineares Homogêneas de Segunda Ordem com Coeficientes Constantes|EDO's de Segunda Ordem Lineares e Homogêneas]] mas, começaremos agora a traçar certas características a respeito da soluções de [[Equações Diferenciais]] Lineares não Homogêneas de Segunda Ordem, da forma:

$$L[y] = y^{\prime\prime} + py^\prime + qy = g(x) \tag{1}$$

Pode ser provar que, dadas duas soluções quaisquer dessa equação $Y_1$ e $Y_2$, a subtração $Y_1 - Y_2$ é solução da seguinte EDO:

$$y^{\prime\prime} + py^\prime + qy = 0 \tag{2}$$

Chamada de **EDO homogênea Associada** à equação $(1)$, podendo ser então expressa como parte de seu conjunto fundamental de soluções, isto é, se $y_1$ e $y_2$ formarem o conjunto solução de $(2)$ vale que:

$$Y_1 - Y_2 = c_1y_1 + c_2y_2$$

A partir disso, podemos chegar ao fato de que:

> A solução geral da equação diferencial $y^{\prime\prime} + p(x)y^\prime + q(x)y = g(x) \tag{1}$ pode ser dada por: 
> $$y = \phi(x) = c_1y_1 + c_2y_2 + Y(x)$$
> Onde $Y(x)$ é uma solução arbitrária da equação e $c_1y_1 + c_2y_2$ é a solução geral da sua equação homogênea associada.

Sendo assim, podemos resolver EDO's não homogêneas de segundo grau seguindo os passos:

1. Encontramos a chamada **Solução Complementar**, a solução geral da sua equação homogênea associada
2.  Encontramos uma única solução $Y(x)$ da EDO não homogênea, denominada de **solução particular**
3. Somamos a Solução Complementar a Solução Particular

Esse processo de parece muito com o que fazíamos para resolver [[Sistemas lineares]] não homogêneos em [[UFPE/2025.1/Álgebra Linear/Álgebra Linear|Álgebra Linear]]. 

Nesse sentido, o primeiro método que veremos é o método dos **Coeficientes Indeterminados**. Esse método consiste basicamente em, a partir da forma do termo não homogêneo da equação, predizer a forma de sua solução, daí, substituindo na EDO uma solução genérica dessa forma, encontrar um sistema linear que, se resolvido, nos dá a tal solução particular, porém, por depender justamente dessa predição da forma da solução particular, esse método, em geral, é usado apenas para EDO's para as quais a associada homogênea é [[EDO's Lineares Homogêneas de Segunda Ordem com Coeficientes Constantes|EDO de coeficientes constantes]] e o termo não homogêneo pertence a uma classe particular de funções, isto é, polinômios, exponenciais, senos e cossenos.


| $g_i(x)$                                                                   | $Y_i(x)$                                                                                                                          |
| -------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| $P_n(x) = a_0x^n + a_1x^{n-1}+ \cdots + a_n$                               | $x^s(A_0x^n +A_1x^{n-1}+ \cdots + A_n)$                                                                                           |
| $P_n(x)e^{\alpha x}$                                                       | $x^s(A_0x^n +A_1x^{n-1}+ \cdots + A_n)e^{\alpha x}$                                                                               |
| $P_n(x)e^{\alpha x}\begin{cases}\sin(\beta x) \\ \cos(\beta x)\end{cases}$ | $x^s(A_0x^n +A_1x^{n-1}+ \cdots + A_n)e^{\alpha x}\cos{\beta x} + x^s(A_0x^n +A_1x^{n-1}+ \cdots + A_n)e^{\alpha x}\sin{}\beta t$ |

Obs: O índice $s$ do termo $x$ é definido como o menor inteiro não negativo (0, 1 ou 2) que garantirá que nenhuma parcela de $Y_i(x)$ é uma solução da equação homogênea associada o que equivale, respectivamente a: $s$ é o número de vezes em que $0$ é uma solução da equação característica da EDO, $s$ é o número de vezes que $\alpha$ é uma raiz da equação característica e $\alpha + i\beta$ é uma solução da equação característica.

Podemos resumir, as diversas sutilezas e "bizus" desse método em alguns passos:

1. Encontre a solução da equação homogênea associada
2. Verifique se os termo não homogêneo $g(x)$ pertence a uma das seguintes classes de função: Exponenciais, Polinômios, Senos, Cossenos, somas ou produtos dessas funções 
3. Se o temos não homogêneo for uma soma de funções, ou seja $g(x) = q_1(x) + \cdots + g_n(x)$, divida a EDO em $n$ subproblemas com a equação $ay^{\prime\prime} + by^\prime + cy = g_i(x)$
4. Para o $i$-ésimo subproblema, suponha uma forma para a  solução particular $Y_i(x)$ consistindo na função apropriada, baseado no termo $g_i(x)$, se essa forma for semelhante a solução da homogênea associada, multiplique-a por $x$, se ainda assim houver uma duplicidade entre esta e a solução da homogênea multiplicamos novamente por $t$ 
5. Encontre a solução parcial para cada um dos subproblemas, a soma de todas essas soluções é uma solução particular da equação não homogênea
6. Somando essa solução particular com a solução geral da EDO teremos a solução geral da EDO linear não homogênea de segunda ordem


