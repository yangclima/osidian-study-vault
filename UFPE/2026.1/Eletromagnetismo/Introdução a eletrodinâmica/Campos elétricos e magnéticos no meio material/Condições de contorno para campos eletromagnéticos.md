As [[Equações de Maxwell]] restringem fortemente o comportamento dos  [[Campo Elétrico|campos elétricos]] e [[Campo Magnético|magnéticos]] nas fronteiras entre dois meios com propriedades diferentes, onde as equações que impõem essas restrições são chamadas de **Condições de Contorno**.

Um dos principais resultados dessas condições é que onda eletromagnéticas nas interfaces dos meios são parcialmente transmitidas e parcialmente refletidas com direções e amplitudes que dependem dos dois meios, dos ângulos de incidência das ondas e de polarizações dos meios.

Campos estáticos também apresentam, na maioria dos casos, diferentes amplitudes e e direções nos dois lados da fronteira e alguns limites apresentam cargas ou correntes superficiais que afetam ainda mais os campos adjacentes.

Para facilitar as considerações a respeito dessas condições de fronteira, dividimos os campos eletromagnéticos em componentes perpendiculares e tangenciais com relação a interface de interesse.

# Componentes perpendiculares

As condições de contorno que governam o comportamento dos componentes perpendiculares de $\vec E$ e $\vec H$ seguem as [[Integrais de superfície|formas integrais]] da [[Lei de Gauss]]:

$$\oint_S(\vec D\cdot \hat n)da = \iiint_V\rho dv \ \ \ \ \text{e} \ \ \ \ \oint(\vec B\cdot \hat n)da = 0 $$

Assumindo um elemento infinitesimal de área da interface entre os dois meios e usando como superfície Gaussiana um cilindro infinitesimal paralelo a esse elemento e atravessando a superfície, estando então, metade acima e metade abaixo da interface, possuindo uma altura $\delta$ que se aproxima de $0$ mais rapidamente que sua área $S$, que também tende a zero e corresponde ao dobro da área $A$ da "tampa" do cilindro, aplicamos a Lei de Gauss para a componente $\vec D_\perp$, perpendicular à superfície, obtendo:

$$\oint_S(\vec D\cdot \hat n)da = (D_{1\perp} - D_{2\perp})A= \iiint_V\rho dv = \rho_SA$$

O que significa que $D_{1\perp} - D_{2\perp} = \rho_S$ onde $\rho_S$ é a densidade de carga superficial $[C\cdot m^{-2}]$ e o cilindro é tão fino que a contribuição de sua superfície lateral para a integral se anula e apenas uma carga superficial $q$ está contida nele, de tal forma que $\rho_S = q/A$. O que queremos dizer com isso é que a componente perpendicular do vetor deslocamento elétrico $\vec D_\perp$ apresenta uma descontinuidade na fronteira de acordo com o valor da densidade superficial de carga $\rho_S$.

Podemos então estabelecer:

$$\hat n \cdot (\vec D_1 - \vec D_2) =\rho_S$$

onde $\hat n$ é o vetor unitário normal a superfície que aponta para dentro do meio $1$, equação que é denominada **Condição de contorno para $\vec D$**.

Como a [[Lei de Gauss para o campo magnético]] é similar a Lei de Gauss para o campo elétrico, mas não há cargas magnéticas, a mesma análise aplicada a $\vec B$ fornece uma condição de contorno

$$\hat n \cdot (\vec B_1 - \vec B_2) = 0$$

Portanto a componente perpendicular do campo magnético deverá ser contínuo em qualquer fronteira, note porém que, caso os meios tenham diferentes [[Permeabilidade|permeabilidades]], apesar do campo $\vec B$ ser contínuo, haverá uma descontinuidade no campo $\vec H$.

# Componentes tangenciais
As condições de contorno que governam as componentes tangenciais dos campos $\vec E$ e $\vec H$ decorrem da [[Lei de Ampére]] e da [[Lei de Faraday]]:

$$\oint_c \vec E \cdot d\vec s = -\dfrac{\partial}{\partial t}\iint_A (\vec B\cdot \hat n)da$$
$$\oint_c \vec B \cdot d\vec s = \iint_A (\vec J + \dfrac{\partial\vec D}{\partial t})d\vec a$$

Podemos aplicar essas equações sobre um contorno  retangular alongado $C$ que atravessa um elemento infinitesimal da fronteira entre os dois meios e tem área $A$, assumimos que a altura desse contorno é $\delta \to 0$  e seu comprimento é $W$ tal que $W >> \delta$ e circulamos esse contorno positivamente com relação a um vetor normal unitário $\hat n_a$, começando pela Lei de Faraday, obtendo:

$$\oint_C \vec E\cdot d\vec s = (\vec E_{1//} - \vec E_{2//})W = -\dfrac{\partial}{\partial t}\iint_A (\vec B\cdot \hat n)da = 0$$

Já que a integral de área de $\vec B$ se aproxima de $0$ na medida que $\delta$ também se aproxima, e como $W \neq 0$, temos que $\vec E_{1//} - \vec E_{2//} = 0$ e portanto, independente do meio, não haverá descontinuidade na componente paralela do [[Campo Elétrico]], e de maneira mais geral, podemos definir:

$$\hat n \times (\vec E_1 - \vec E_2) = 0$$

note porém, que, no caso em que os meios tem diferentes [[Permissividade|permissividades]], apesar do campo $\vec E$ ser contínuo, o campo $\vec D$ apresentará uma descontinuidade.

Integrando a [[Lei de Ampére]] de modo similar, obtemos, assumindo que o contorno $C$ é escolhido num plano perpendicular a corrente superficial $\vec J_s$ e é percorrido no sentido horário, obtemos:

$$\oint_C \vec H\cdot d\vec s = (\vec H_{1//}-\vec H_{2//})W = \iint_A(\vec J + \dfrac{\partial\vec D}{\partial t})d\vec a = \vec J_S W$$

Já que a medida que $\delta$ tende a $0$, $\dfrac{\partial\vec D}{\partial t}$ se aproxima de zero, mas não a integral de $\vec J$ sobre a área, que ocupa uma camada superficial fina, e portanto, $\vec H_{1//}-\vec H_{2//} = \vec J_S$, ou, de maneira mais geral:

$$\hat n \times (\vec H_1 - \vec H_2) = \vec J_s$$

isto é, o campo magnético apresentará uma descontinuidade na interface entre dois meios, caso haja uma corrente superficial não nula nessa interface, situação que não ocorre em um meio isolante, já que $\vec J_S =0$.

# Caso especial: Condutores Perfeitos
Um caso específico que pode ser interessante de analisar são os condutores perfeitos, onde aproximamos que $\sigma$, a [[Condutividade]] do meio, tende ao infinito. Dentro de um meio desse tipo, os campos devem ser nulos já que quando expostos a um campo elétrico qualquer $\vec E$, surge uma corrente enorme $\vec J = \sigma\vec E$ que rapidamente neutraliza esse campo, na maioria das vezes, instantaneamente, além disso, sabemos das [[Equações de Maxwell no domínio do tempo|Equações de Maxwell]] que, como vale que $\vec\nabla \times \vec E = -\dfrac{\partial \vec B}{\partial t}$ e $\vec E = 0$, desde que o condutor tenha sido "criado" sem nenhum campo magnético interno ele permanecerá sem ele. 

Por mais absurdo que pareça considerar $\sigma \to \infty$, esse caso especial é muito relevante para os condutores reais já que a maioria dos metais apresentam condutividade suficiente para permitir que $\vec J$ e $\rho_s$ cancelem o campo elétrico interno, mesmo que não seja de forma instantânea, em metais, esse relaxamento é suficientemente rápido para que consideremos que as condições de contorno de condutores perfeitos se aplicam.

Essas condições são:

$$\hat n \cdot \vec B = 0 $$
$$\hat n \cdot \vec D = \rho_S$$
$$\hat n \times \vec E = 0$$
$$\hat n \times \vec H = \vec J_S$$

Essas condições implicam que campos elétricos podem apenas ser perpendiculares a um condutor perfeito, enquanto o campos magnéticos podem apenas ser tangenciais a esses condutores, além disso, os campos magnéticos nesses casos estão sempre associados com as correntes superficiais que são numericamente iguais a $\vec H$, enquanto os campos elétricos estão sempre associados a uma densidade de carga superficial $\rho_S$  que é numericamente igual a $\vec D$, este que aponta para fora do meio caso $\rho_S > 0$ e para dentro do meio no caso oposto.