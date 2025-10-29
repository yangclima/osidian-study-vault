Assim como temos no cálculo unidimensional um [[Primeiro teorema fundamental do cálculo|Teorema fundamental]], para [[Integrais de linha]] temos também o seguinte Teorema fundamental:
$$
\int_C \nabla f \cdot d\vec{r} = f(\vec{r}(b))-f(\vec{r}(a))
$$
Essa propriedade pode ser utilizada sempre que tivermos um [[Campos vetoriais|campo vetorial]] $\vec{F}$conservativo, ou seja, onde existe uma função potencial $f$ tal que $\vec{F} = \nabla f$, a existência dessa função potencial implica uma independência de caminho, ou seja, qualquer que seja a curva entre dois pontos $a$ e $b$.

Ter um campo conservativo implica também que, para qualquer curva fechada num campo conservativo, temos $\int \vec F \,d\vec r = 0$, o interessante é que a implicação é bilateral, ou seja, dada uma região $D$, se $\int \vec F \,d\vec r$ é independente de caminho em $D$, então existe  $f$ tal que $\vec{F} = \nabla f$ e portanto o campo é conservativo.

De forma análoga, um campo $F(x,y,z) = P(x,y,z)\hat{i} + Q(x,y,z)\hat{j} + R(x,y,z)\hat{k}$ 
conservativo tem derivadas cruzadas iguais, ou seja:
$$
\dfrac{\partial P}{\partial y} = \dfrac{\partial Q}{\partial x}, \dfrac{\partial P}{\partial z} = \dfrac{\partial R}{\partial x} \text{ e } \dfrac{\partial Q}{\partial z} = \dfrac{\partial R}{\partial y}
$$
Para regiões simplesmente conexas, a recíproca é verdadeira.