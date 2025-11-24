Como a [[Lei de Coulomb|Força elétrica]] é uma força conservativa, isso nos permite pensar em alguns conceitos úteis relacionados a ela. Digamos que, por exemplo, queremos descobrir o trabalho exercido por um [[Campo Elétrico]] em uma partícula pontual de carga $q$, temos então:
$$
W = \int \limits_a^b \vec{F}_e \cdot d\vec{r} = \int \limits_a^b \dfrac{kqQ}{r^2}\cdot d\vec{r} = kqQ \int \limits_a^b \dfrac{d\vec{r}}{r}
$$
Porém, sabemos lá das aulas de cálculo que quando lidamos com [[Campos vetoriais]] conservativos podemos encontrar uma função potencial, $U$ tal que $\vec{F} = \nabla U$, na física, chamamos essa função de **Energia Potencial**, o análogo dessa função para a força gravitacional é a [[Energia Potencial Gravitacional]], a grande vantagem dessa função é permitir o cálculo do trabalho da seguinte forma:

$$
W = -\Delta U = U_i - U_f
$$

É necessário entretanto para dar significado físico a essa função $U$ tomar como ponto de referência $P$ tal que $U(P) = 0$, ao lidarmos com força elétrica muitas vezes é muito comum e muitas vezes útil considerar $U(\infty) = 0$, dessa forma podemos escrever:

$$
U(r) = U(r) - U(\infty) = \int \limits_\infty^r \dfrac{kqQ}{r^2} d\vec{r} = \left[\dfrac{kQq}{r}\right]^r_\infty = \dfrac{kQq}{r}
$$

O interessante é que assim, sabemos que o trabalho de uma força elétrica sobre uma carga pontual não depende do caminho que essa partícula percorre o que abre uma infinidade de possibilidades. Podemos também calcular a energia potencial $U$ de um sistema de múltiplas de partículas, grandeza que pode ser pensada como a energia necessária para reunir estas partículas na posição em que elas estão, imagine então que adicionamos uma partícula por vez, de forma que as partículas que já estão no lugar influenciam a adição das próximas, temos então:

$$
U = k\sum_{i=1}^N \sum_{j>i}^N \dfrac{q_iq_j}{r_{ij}}
$$

O problema é que só podemos calcular a energia potencial elétrica par pares de partículas entretanto já vimos que uma carga modifica o espaço através de um campo elétrico independente da existência ou não de outra carga (Aquela velha discussão da [[Ação a distância versus Ação intermediada]]), podemos então fazer algo semelhante  ao que fizemos para obter o campo elétrico, criaremos então uma medida de energia potencial por carga, medida então em Joules por Coulomb, unidade essa apelidada de **Volt**, chamada **potencial elétrico** e definida da seguinte maneira:

$$
V = \dfrac{U}{q} \implies dV = \dfrac{dU}{dq}  \implies \Delta V = \int \limits_a^b \vec{E} \cdot d\vec{r} = V_f - V_i
$$

Além disso, da mesma forma que fizemos para a energia potencial podemos tomar um referencial $V(\infty) = 0$, o que nos  permite definir:

$$
V(r) = V(r) - V(\infty) = \int \limits_\infty^r \vec{E} \cdot d\vec{r} = \dfrac{kQ}{r}
$$

Uma outra sacada importante é que podemos utilizar dessa função de $V$ para calcular o potencial de corpos extensos, escrevendo:

$$
dV = \dfrac{kdq}{r} \implies V = \int_{corpo} \dfrac{kdq}{r}
$$

O mesmo pode ser utilizado para cargas pontuais, utilizando, ao invés de uma integral, um somatório:

$$
V(r) = k\sum_{i=1}^N \dfrac{q_i}{r_i}
$$

Em suma, vale notar a grande importância do potencial elétrico, uma vez que este funciona como abstração, permitindo trabalhar com valores escalares ao invés de vetoriais o que permite "retirar da equação" algumas dificuldades de cálculo que ocorrem devido ao fator vetorial.