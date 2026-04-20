Ao discutir as propriedades gerais de [[Equações diferenciais Lineares de Segunda Ordem]] é conveniente utilizar uma notação especial: **O operador diferencial**. 

Sejam $p$ e $q$ duas funções de $x$ contínuas em um intervalo $I$ aberto, então, para qualquer função $\phi$ com [[Derivada|derivadas de primeira]] e [[Derivadas parciais|segunda ordem]] bem comportadas em $I$, definimos o operador diferencial $L$ como:

$$L[\phi] = \phi^{\prime\prime} + p\phi^{\prime} + q\phi$$

De tal forma que o resultado da aplicação de $L$ em uma função qualquer $\varphi$ é uma outra função $L[\varphi]$, com valor $L[\varphi](x)$ no ponto $x$ dado por: 

$$L[\varphi](x) = \phi^{\prime\prime}(x) + p(x)\phi^{\prime}(x) + q(x)\phi(x)$$

Onde inicialmente estaremos interessados em funções homogêneas, ou seja, $L[y] = 0$. 

Aqui, vale uma extensão do Teorema da [[Existência e Unicidade das Soluções]], valendo que: 

> Considerando o PVI $y^{\prime\prime} + py^\prime + qy = g$, $y(x_0)=y_0$, $y^\prime(x_0) = y^\prime_0$, em que as funções $p$, $q$ e $g$ são contínuas em um intervalo aberto $I$ que contém $x_0$, existe uma e apenas uma solução $y = \varphi(x)$ para esse problema e esta solução existe em todo o intervalo $I$.

Além disso, o [[UFPE/2026.1/Cálculo 4/Equações Diferenciais de Primeira Ordem/Teorema da Superposição|Teorema da Superposição]] vale aqui, o que deve-se a linearidade das equações com que trabalhamos, de tal forma que se encontrarmos duas soluções $y_1$ e $y_2$ para uma EDO Linear Homogênea de 2ª Ordem, qualquer outra solução possível poderá ser expressa como combinação linear dessas duas soluções, com a nova notação, isso equivale a:

$$L[c_1y_1 + c_2y_2] = c_1L[y_1] + c_2L[y_2]$$

Sabemos, então, que, para uma EDO linear homogênea de segunda ordem, é possível, a partir de duas soluções $y_1$ e $y_2$, formar uma família infinita de soluções dessa equação por meio de combinações lineares. O próximo passo é verificar se todas as soluções dessa EDO específica estão incluídas na família gerada por $y_1$ e $y_2$, isto é, se essas funções, sendo linearmente independentes, formam uma [[Bases ortogonais|base]] para o [[Sistemas lineares#Conjunto solução|conjunto solução]] da equação. Esse conjunto solução pode, por sua vez, ser interpretado como um  [[Espaços vetoriais|espaço vetorial]] de dimensão 2, isto é, um [[Subespaços Vetoriais|subespaço]] do espaço de funções definido no intervalo considerado.

Ou, de forma resumida, verificar se a família gerada pelas funções é capaz de satisfazer qualquer condição inicial do problema de valor inicial, o que exige que:

$$
\begin{cases}
c_1y_1(x_0) + c_2y_2(x_0) = y_0\\
c_1y_1^\prime(x_0) + c_2y_2^\prime(x_0) = y_0^\prime 
\end{cases}
$$

O que é verdade se o determinante:

$$
W = \begin{vmatrix}
y_1 & y_2 \\
y_1^\prime & y_2^\prime
\end{vmatrix} = y_1y_2^\prime - y_2y_1^\prime \neq 0
$$

Esse determinante é chamado de **Determinante Wronskiano** ou simplesmente **Wronskiano** das soluções $y_1$, $y_2$ e se ele for diferente de $0$ isso implica dizer que as soluções $y_1$ e $y_2$ são linearmente independentes.

Assim, chegamos a conclusão de que para encontrar a solução geral de uma EDO linear de segunda ordem homogênea precisamos encontrar duas soluções dessa equação que sejam linearmente independentes, isto é, duas funções $y_1$ e $y_2$ cujo Wronskiano seja não nulo.

Ao longo do curso trabalharemos ainda com equações diferenciais lineares de segunda ordem homogêneas que possuem solução imaginária, nesse caso, é importante ter em mente o seguinte fato:

Seja

$$L[y] = \ddot{y} + p\dot{y} + qy = 0$$

Em que $p$ e $q$ são funções reais contínuas, se $y = u + iv$ for uma solução complexa da EDO, então sua partes real e imaginária $u$ e $v$ são também soluções da equação.