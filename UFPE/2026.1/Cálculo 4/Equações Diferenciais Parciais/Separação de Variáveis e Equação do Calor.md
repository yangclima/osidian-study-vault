Para alguns problemas físicos, não é suficiente a descrição dada pelas [[equações diferenciais]] ordinárias, temos mais de uma variável independente e por isso entram em cena relações e equações definidas com [[Derivadas parciais]] com, por exemplo, uma variável temporal $t$ e uma variável espacial $x$ ambas independentes. O primeiro dos principais casos em que essa descrição é necessárias é o caso da condução de calor em um barra:

![[c4_002.png]]

Tomadas as simplificações de que a secção circular da barra é pequena o suficiente para que a temperatura $u$ seja uniforme em qualquer secção ao longo do eixo da barra e que a condução de calor só se dê ao longo do eixo $x$, temos como fato que a condução térmica nessa barra obedece a relação:

$$\alpha^2u_{xx} = u_{t}\,; \ x\in [0,L]\,; t > 0 $$

Onde $\alpha^2$ é uma constante que depende das propriedades físicas da barra, além disso, assumimos uma espécie de conjunto de valores iniciais que restringirão nossos resultados:

$$
\begin{cases}
u(0,t) = 0 \\
u(L,t) = 0 \\
u(x,0) = f(x) 
\end{cases}
$$

As duas primeiras dizem algo como: Submetemos as extremidades da barra a uma mesma temperatura e a terceira diz: No $t=0$ a distribuição da temperatura na barra é descrita por uma função $f(x)$.

Assim, assumindo que $u(x,t) = X(x)T(x) = XT$ ficamos com:

$$\alpha^2X^{\prime\prime}T = XT^\prime$$

Separando as variáveis, dividindo ambos os membros por $\alpha^2XT$:

$$\dfrac{X^{\prime\prime}}{X}= \dfrac{1}{\alpha^2}\dfrac{T^\prime}{T}$$

Para satisfazer essas igualdade, deve ser verdadeira a relação:

$$\dfrac{X^{\prime\prime}}{X}= \dfrac{1}{\alpha^2}\dfrac{T^\prime}{T} = -\lambda$$

E essa EDP pode ser separada no seguinte sistema:

$$\begin{cases}X^{\prime\prime}+ \lambda X = 0 \\ T^\prime + \lambda T = 0\end{cases}$$

De forma que o produto de uma solução da primeira equação por uma solução da segunda equação é uma solução da equação diferencial parcial da condução de calor, porém ainda temos a restrição

$$u(0,t) = X(0)T(t) = 0$$ 
Mas pela própria interpretação física rejeitamos a solução trivial $T(t) = 0$ de modo que as únicas soluções triviais que nos restam são:

$$X_n(x) = \sin{\left(\dfrac{n\pi x}{L}\right)}\,; n \in \mathbb{N}$$

Cada uma associada a um valor:

$$\lambda_n = \dfrac{n^2\pi^2}{L^2}\,; n\in \mathbb{N}$$

para o qual:

$$T(t) = e^{-(n^2 \pi^2\alpha^2t)/L}\,; n\in\mathbb{N} $$

Portanto, as soluções da nossa EDP são todas as funções:

$$u_n(x,t) = e^{-(n^2 \pi^2\alpha^2t)/L}\sin{\left(\dfrac{n\pi x}{L}\right)}\,; n\in\mathbb{N}$$

Conjunto chamado de soluções fundamentais da equação, de modo que, voltando as restrições iniciais teremos, utilizando o mesmo que para as [[Equações diferenciais Lineares de Segunda Ordem]], uma combinação linear de todas as soluções possíveis, teremos:

$$u(x,t) = \sum_{n=1}^\infty c_ne^{-(n^2 \pi^2\alpha^2t)/L}\sin{\left(\dfrac{n\pi x}{L}\right)}$$

Onde os coeficientes $c_n$ são constantes a definir de  forma que assumindo a condição inicial de $u(x,0) = f(x)$:

$$u(x,t) = \sum_{n=1}^\infty c_n\sin{\left(\dfrac{n\pi x}{L}\right)}$$

De modo que os coeficientes deverão ser:

$$c_n = \dfrac{2}{L}\int_0^L{f(x)\sin{\left(\dfrac{n\pi x}{L}\right)}dx}$$

