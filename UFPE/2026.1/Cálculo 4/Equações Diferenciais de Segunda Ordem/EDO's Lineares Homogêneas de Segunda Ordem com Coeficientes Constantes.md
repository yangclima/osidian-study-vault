Para as [[Equações diferenciais Lineares de Segunda Ordem]], dizemos que se trata de uma **EDO de coeficientes constantes** quando, para a forma geral

$$p(x)y^{\prime\prime} + q(x)y^\prime + r(x)y = 0$$

As funções $p(x)$, $q(x)$ e $r(x)$ são constantes dadas $a$, $b$ e $c$, respectivamente, isto é, equações diferenciais da forma:

$$ay^{\prime\prime} + by^\prime + cy = 0$$

Para resolver esse tipo de equação, note que estamos buscando uma função de $x$ tal que suas [[Derivada|derivadas de primeira]] e [[Derivadas de Ordem Superior|segunda ordem]] sejam iguais a ela, a menos de uma constante, o que nos dá como candidata óbvia a função $y = e^x$, ou, de maneira mais geral $y = e^{rx}$ onde $r$ é uma constante qualquer, um parâmetro, nesse caso, temos $y^\prime = re^{rx}$ e $y^{\prime\prime} = r^2e^{rx}$, e nesse caso, substituindo na nossa EDO:

$$ar^{2}e^{rx} + bre^{rx} + ce^{rx} = 0 \implies (ar^{2} + br + c)e^{rx} = 0$$

Nesse caso, resolver a EDO se torna simplesmente questão de resolver uma equação do segundo grau em $r$, em geral:

$$ar^{2} + br + c = 0$$

Essa equação é denominada **equação característica** da nossa EDO, de tal maneira que se um determinado valor $r_1$ é uma raiz dessa equação do segundo grau, então, $y = e^{r_1x}$ é uma solução para nossa [[Equações Diferenciais|equação diferencial]]. 

Como a equação característica é uma equação clássica do segundo grau, recairemos sempre sob 3 casos possíveis:

1. A equação possui duas raízes $r_1,r_2 \in \mathbb{R}$ 
2. A equação possui uma única raiz $r\in \mathbb{R}$ com multiplicidade $2$
3. A equação possui duas raízes [[Números Complexos|Complexas e conjugadas]] $r,\overline{r} \in \mathbb{C}$ 

# Caso 01: $\Delta > 0$
No caso $1$, teremos como soluções da EDO, as funções $y_1 = e^{r_1x}$ e $y_2 = e^{r_2x}$ e também, pela linearidade, será solução qualquer função $y = c_1e^{r_1x} + c_2e^{r_2x}$ onde $c_1,c_2 \in \mathbb{R}$, que, pela ampla generalidade é denominada **solução geral** da nossa equação diferencial do segundo grau, o desafio nesse caso é então encontrar os valores de $r_1$ e $r_2$ através da equação característica, e teremos então:

$$
\begin{cases}
r_1 = \dfrac{-b+\sqrt{\Delta}}{2a} \\ \\
r_2 = \dfrac{-b-\sqrt{\Delta}}{2a}
\end{cases}
$$

# Caso 02: $\Delta < 0$
Para o caso 2, precisaremos recorrer a [[Fórmula de Euler]] e ao fato que vimos ao pensar em [[Soluções de Equações Lineares Homogêneas]] de que se uma função complexa $y = u + vi$ é solução de uma EDO desse tipo, então $u$ e $v$ são também soluções dessa EDO, dessa forma, precisamos encontrar apenas uma raiz $r = \dfrac{-b + \sqrt\Delta}{2a}$ que será um [[Números Complexos|número complexo]] $r = \dfrac{-b + \sqrt{|\Delta|}i}{2a}$ que podemos denotar por $r = \lambda +i\mu$ e então será solução da nossa EDO a seguinte função:

$$y = u + iv = e^{rx} = e^{(\lambda +i\mu)x}$$

Que como a  fórmula de Euler, se transformará em:

$$y = u + iv = e^{\lambda x}(\cos{(\mu x}) + i\sin{((\mu x)})$$

De tal modo que tanto $u = e^{\lambda x}\cos(\mu x)$ e $v = e^{\lambda x}\sin(\mu x)$ são soluções da EDO linearmente independentes que então formam o nosso conjunto solução:

$$
y = c_1 e^{\lambda x}\cos(\mu x) + c_2e^{\lambda x}\sin(\mu x)
$$

Quanto a outra raiz da equação característica, nesse caso sendo $\bar r$, o [[Aritmética de números complexos#Conjugação|conjugado complexo]] de $r$, ela já é contemplada pelo nosso conjunto solução escolhendo um valor negativo para $c_2$.
# Caso 03: $\Delta = 0$
No caso onde $\Delta = 0$ não conseguimos dois valores de $r$ para obter duas [[Soluções de Equações Lineares Homogêneas]] linearmente independentes, nesse caso, precisamos de uma outra solução que pode ser obtida pelo método de redução de ordem, procurando uma função $y_2 = A(x)y_1$ que seja também solução da EDO, nesse caso, substituindo na equação onde $y_2^\prime = A^\prime y_1 + y_1^\prime A$ e $y^{\prime\prime}_2 = A^{\prime\prime}y_1 + 2y_1^\prime A^\prime + y_1^{\prime\prime}A$:

$$
a(A^{\prime\prime}y_1 + 2y_1^\prime A^\prime + y_1^{\prime\prime}A) + b(A^\prime y_1 + y_1^\prime A) + c(A^\prime y_1) = 0
$$
$$
a(A^{\prime\prime}e^{rx} + 2re^{rx} A^\prime + r^2e^{rx}A) + b(A^\prime e^{rx} + re^{rx} A) + c(A e^{rx}) = 0
$$
$$
a(A^{\prime\prime} + 2r A^\prime + r^2A) + b(A^\prime + r A) + c(A) = 0
$$
$$
a(A^{\prime\prime} + 2r A^\prime + r^2A) + b(A^\prime + r A) + c(A) = 0
$$
$$
aA^{\prime\prime} + (2ar+ b)A^\prime + (ar^2 + br + c)A = 0
$$

Como $ar^2 + br + c = 0$ então:

$$
aA^{\prime\prime} + (2ar+ b)A^\prime= 0
$$

Mas $r = -b/2a$ então:

$$
aA^{\prime\prime} + (-b+ b)A^\prime= 0
$$

$$
aA^{\prime\prime} = 0 \implies A^\prime = C_1x \implies  A = C_1x + C_2
$$

Mas como qualquer solução nos basta, então, utilizamos $C_1 = 1$ e $C_2 = 0$ e checamos com o wronskiano, provando que $y_1$ e $y_2 = Ay_1 = xe^{rx}$ são linearmente independentes, de tal forma que nossa solução geral é:

$$y =C_1e^{rx} + C_2xe^{rx}$$