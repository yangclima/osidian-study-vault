O Teorema de Stokes, ou Teorema do Rotacional é um teorema poderoso que permite relacionar uma [[Integrais de superfície|integral de superfície]] sobre uma superfície $\mathcal S$ a uma [[Integrais de linha|integral de linha]] sobre uma curva $\mathcal C$, fronteira de $\mathcal S$. O teorema diz o seguinte:

> Seja $\mathcal S$ uma superfície orientada, suave por partes, cuja fronteira é formada por uma curva $\mathcal C$, fechada, simples, suave e positivamente orientada e $\vec F$ um [[Campos vetoriais|campo vetorial]] com componentes que possuem [[Derivadas parciais]] contínuas em seu domínio, vale que:
> $$ \int_\mathcal C \vec F \cdot d\vec r= \iint \limits_{\mathcal S}(\vec \nabla \times \vec F)\cdot d\vec S$$
> OBS: Lembre-se que $\vec \nabla \times \vec F$ é o [[Rotacional]] de $\vec F$.

É possível provar que o [[Teorema de Green]] é um caso específico do Teorema de Stokes e a sua utilidade é parecida, dada uma complicada integral de linha queremos poder calcular seu valor de maneira mais fácil com uma integral de superfície, ou dada uma complicada integral de superfície queremos poder calculá-la mais facilmente usando uma integral de linha. 

Um fato sutil mas importante é que, dada uma curva $\mathcal C$, fronteira da superfície $\mathcal S_1$ se uma outra superfície $\mathcal S_2$ é também limitada por $\mathcal C$, então:

$$ 
\iint \limits_{\mathcal S_1}(\vec \nabla \times \vec F)\cdot d\vec S = \int_\mathcal C \vec F \cdot d\vec r = \iint \limits_{\mathcal S_2}(\vec \nabla \times \vec F)\cdot d\vec S
$$

Uma coisa que acaba por tornar esse teorema um pouco menos efetivo é a necessidade de realizar, de qualquer forma, uma parametrização.