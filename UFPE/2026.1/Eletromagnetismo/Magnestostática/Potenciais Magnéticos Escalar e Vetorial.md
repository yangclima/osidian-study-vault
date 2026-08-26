Já vimos que podemos simplificar alguns problemas envolvendo [[Campo Elétrico]] através do uso do [[Potencial elétrico]], de forma similar, podemos definir o Potencial Magnético, que pode ser tanto escalar $V_m$ quanto vetorial $\vec A$.

Pela definição de [[Campos vetoriais]] conservativos, no [[Cálculo 3]], sabemos que só admitem função potencial escalar os campos conservativos, isto é, campos cujo [[Rotacional]] é nulo, dessa maneira, usando as [[Equações de Maxwell]], mais especificamente a [[Lei de Ampére]], teremos como condição para que o [[Campo Magnético]] admita um potencial escalar  $V_m$ que:

$$\vec\nabla\times \vec H = \vec J = 0$$

De tal modo que, em regiões em que $\vec J = 0$ podemos escrever:

$$\vec H = -\vec \nabla V_m$$

Caso em que o campo magnético satisfaz a equação de Laplace, valendo que:

$$\nabla^2 V_m = 0$$

Em casos onde essa condição de [[Corrente]] nula não é satisfeita ainda podemos definir um vetor potencial magnético $\vec A$ tal que:

$$\vec B = \vec \nabla \times \vec A$$

Que define-se, de forma similar ao potencial elétrico em relação com a [[Lei de Coulomb]], mas com relação a [[UFPE/2025.2/Física 3/Magnetostática/Lei de Biot-Savart|Lei de Biot-Savart]] por:

$$\vec A = \int_L\dfrac{\mu_0Id\vec l}{4\pi R}$$
$$\vec A = \int_S\dfrac{\mu_0\vec K dS}{4\pi R}$$
$$\vec A = \int_V\dfrac{\mu_0\vec J dv}{4\pi R}$$

E a partir do [[Teorema de Stokes]] definimos o [[Fluxo magnético]] como:

$$\psi = \oint_L \vec A \cdot d\vec l$$

A ideia básica é então utilizar uma dessas duas relações para calcular grandezas como o fluxo magnético, ou encontrando primeiro $\vec B$ e a partir dele o fluxo, ou aplicando diretamente a última relação.