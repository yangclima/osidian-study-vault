Para encontrar a tensão, também chamada de Diferença de Potencial ou de diferença no [[Potencial elétrico]] $\Upphi$, medida em Volts, entre dois pontos quaisquer do espaço, basta [[Integrais de linha|integrar]] o [[Campo Elétrico]] $\vec E$ ao longo de qualquer caminho entre os dois pontos, desde que $\vec E$ seja eletrostático ($\vec \nabla\times\vec E = 0$).

Assim, para quaisquer dois pontos $r_1$ e $r_2$ vale que:

$$
\Upphi(r_1) - \Upphi(r_2) = -\int_{r_1}^{r_2} \vec E \cdot d \vec r
$$

de forma similar, podemos tomar como convenção que $\Upphi(\infty) = 0$ atribuindo assim a cada ponto no espaço um valor absoluto do potencial elétrico ou da tensão, o que nos dá que para um campo elétrico gerado por uma [[Carga]] pontual $Q$ no vácuo a uma distância $r$:

$$
\Upphi(r) = \dfrac{Q}{4\pi\varepsilon_0r}
$$

Vale ressaltar, no entanto, que esse valor absoluto não tem significado físico, o que importa mesmo é a diferença de potencial entre os dois pontos, que se preserva independente da convenção.

Perceba que só faz sentido pensar em um potencial para um campo que seja conservativo, daí a exigência de que $\vec E$ seja eletrostático, uma vez que, nesse caso, assumimos, pela [[Lei de Faraday]] para $\frac{\partial}{\partial t} = 0$:

$$
\oint \vec E \cdot d\vec s = -\frac{\partial}{\partial t}\iint \vec B\cdot d\vec a = 0
$$

Por outro lado, caso haja um variação temporal do [[Fluxo magnético]], nossa ideia de potencial elétrico deixa de fazer sentido globalmente  uma vez que o campo elétrico $\vec E$ não é conservativo.

Um fato notável é que as [[Equações de Maxwell]] tem caráter linear, dessa forma o princípio da superposição se aplica e se torna uma tarefa fácil somar as contribuições de múltiplas distribuições de carga encontrando o potencial total.