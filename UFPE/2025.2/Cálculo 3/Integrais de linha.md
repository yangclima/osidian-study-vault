Ao estudarmos as [[Integral definida|integrais unidimensionais]] entendemos como dividir um intervalo em infinitas partes infinitesimais pode nos ajudar a calcular a área sob o gráfico de uma função, um procedimento análogo pode ser usado como argumento geométrico para entender um novo conceito: **As integrais de linha**, veja:

> Dada uma [[Curvas|curva]] $\vec{r}(t) = x(t)\hat{i} + y(t)\hat{j} + z(t)\hat{k}$ para $t \in [a,b]$ e uma função $f(x,y,z)$ definida sob esta curva (Ou seja, o domínio de $f$ inclui $C$), a integral de $f(x,y,z)$ sobre $C$ é definida como
> $$ \int_C f(x,y,z)\,ds = \int_a^b f(x(t),y(t),z(t))\sqrt{\left(\dfrac{dx}{dt}\right)^2 + \left(\dfrac{dy}{dt}\right)^2 + \left(\dfrac{dz}{dt}\right)^2}\,dt$$

Muitas vezes essa integral também é pode ser escrita na seguinte notação:

> $$\int_C f(x,y,z)\,ds = \int_C f(\vec{r}(t))|\vec{r}^\prime(t)|\,dt$$

Perceba que o conceito é simples e muito parecido com oque é abordado no cálculo unidimensional, nós dividimos a curva $C$ em pedaços infinitesimais e multiplicamos cada pedaço por sua imagem, a diferença aqui é que o comprimento de cada pedaço infinitesimal é tridimensional.

Podemos estender esse conceito, utilizando da mesma intuição geométrica para calcular outras operações sobre uma curva $C$, por exemplo, dado um [[Campos vetoriais|campo vetorial]] $\vec{F}(x,y,z)$, podemos, dividindo $C$ em pedaços infinitesimais calcular o produto vetorial entre cada um desses pedaços (O vetor tangente a curva, por aproximação) e o campo vetorial, o que tem amplo significado em diversas áreas e problemas da física (Trabalho, por exemplo). Temos, portanto:

> $$ \int_C F(x,y,z) \cdot T(z,y,z)\,ds = \int_C F(\vec{r}(t))\cdot \dfrac{\vec{r}^\prime(t)}{|\vec{r}^\prime(t)|}|\vec{r}^\prime(t)|dt = \int_C F(\vec{r}(t))\cdot \vec{r}^\prime(t) dt$$

Muitas vezes essa integral é escrita na seguinte notação:

> $$ \int_C F(x,y,z) \cdot T(z,y,z)\,ds = \int_C f(\vec{r}(t))d\vec{r}(t)$$


A resolução de integrais de linha se resume então em, a partir de uma [[Parametrização de curvas|parametrização]] de uma curva $C$ substituir os termos nas formas vistas acima e então, resolver a integral.
