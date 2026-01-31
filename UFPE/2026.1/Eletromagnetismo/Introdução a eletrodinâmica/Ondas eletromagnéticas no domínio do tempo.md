Um dos resultados mais profundos das [[Equações de Maxwell no domínio do tempo|Equações de Maxwell]] é a previsão da existência de **[[Ondas Eletromagnéticas Planas|ondas eletromagnéticas]] auto-propagantes**, isto é, campos elétricos e magnéticos capazes de se sustentar mutuamente no espaço **mesmo na ausência de cargas e correntes**.

Essa previsão não é empírica: ela emerge diretamente da estrutura matemática das equações, a partir de constantes medidas em laboratório: a **permissividade elétrica** $\varepsilon_0$ e a **permeabilidade magnética** $\mu_0$ do vácuo.

No vácuo, não há [[Carga|cargas livres]]  nem [[Corrente|correntes elétricas]]: então, as [[Equações de Maxwell]] se tornam:

$$
\nabla \cdot \vec E = 0
$$
$$
\nabla \cdot \vec B = 0
$$
$$
\nabla \times \vec E = -\mu_0\frac{\partial \vec H}{\partial t}
$$
$$
\nabla \times \vec B = \varepsilon_0\frac{\partial \vec E}{\partial t}
$$

Podemos então eliminar $\vec H$ dessas equações tomando o [[Rotacional]] de ambos os lados da [[Lei de Faraday]]:

$$
\nabla \times (\nabla \times \vec E) = -\nabla \times\left(\mu_0\frac{\partial \vec H}{\partial t}\right) = -\mu_0\frac{\partial (\nabla \times \vec H)}{\partial t}
$$

Então, substituindo $\nabla \times \vec H$ de acordo com a [[Lei de Ampére|lei de Ampére-Maxwell]]:

$$
\nabla \times (\nabla \times \vec E) = -\mu_0\frac{\partial}{\partial t}\left(\varepsilon_0\frac{\partial \vec E}{\partial t}\right) = -\mu_0\varepsilon_0\frac{\partial^2 \vec E}{\partial t^2}
$$

Por fim, usando a relação bem conhecida $\nabla \times (\nabla \times \vec A) = \nabla(\nabla \cdot \vec A) - \nabla^2\vec A$ (Chamamos $\nabla^2$ de Laplaciano) obtemos:

$$
\nabla(\nabla \cdot \vec E) - \nabla^2\vec E = -\mu_0\varepsilon_0\frac{\partial^2 \vec E}{\partial t^2}
$$

Porém, pela [[Lei de Gauss para Cargas|Lei de Gauss]] para o vácuo $\nabla \cdot \vec E = 0$, nesse caso:

$$
\nabla^2\vec E -\mu_0\varepsilon_0\frac{\partial^2 \vec E}{\partial t^2} = 0
$$

Essa equação é conhecida como **Equação de ondas eletromagnéticas**, cujas soluções são [[Campo Elétrico|campos elétricos]] $\vec E(\vec r, t)$ quaisquer que são funções do vetor posição $\vec r = x\hat x + y\hat y + z\hat z$ e do tempo  $t$ para os quais a derivada espacial segunda é proporcional a derivada temporal segunda por uma constante de proporcionalidade qualquer.

A equação é então satisfeita por qualquer função que tenha igual dependência espacial e temporal com uma constante multiplicativa, por exemplo, funções arbitrárias de argumento $(x \pm ct)$ ou $(x/c \pm t)$ onde $c$ é uma constante qualquer a ser determinada.

Uma solução desse tipo é:

$$
\vec E(\vec r, t) = \vec E(x - ct) =  E_x(x - ct)\hat x
$$

Onde $E_x(x - ct)$ é uma função arbitrária que representa a forma de onda e que tem o mesmo formato a menos de um deslocamento no eixo $\hat x$ a qualquer momento do tempo $t$.

Apesar dessa função satisfazer a equação, uma função arbitrária $E_x$ não satisfaz a [[Lei de Gauss]], isto é:

$$
\nabla \cdot \vec E = \frac{\partial E_x}{\partial x} \neq 0
$$

Porém, uma função do tipo:

$$
\vec E(x, t) =  E_y(x - ct)\hat y \ \ \text{ou} \ \ \vec E(x, t) =  E_z(x - ct)\hat z
$$

Isto é, orientada perpendicularmente a direção de propagação, satisfaz tanto a nossa equação de ondas eletromagnéticas quanto as [[Equações de Maxwell]].

Por exemplo, no caso em que $\vec E(x, t) =  E_y(x - ct)\hat y$ , independente de $x$ ou de $y$ nós temos o que chamamos de [[Ondas Eletromagnéticas Planas|Onda Eletromagnética Plana]] Uniforme, dizemos também que essa onda é **polarizada em $y$** já que esta é a direção do seu [[Campo Elétrico]].

Além disso, para que $\vec E(x, t) =  E_y(x - ct)\hat y$ satisfaça a equação de onda precisamos que:

$$
c = \frac{1}{\sqrt{\mu_0\varepsilon_0}} = 2.998\times 10^8 \ m\cdot s^{-1}
$$

Nesse caso, $c$ é a constante que equivale a velocidade da luz no vácuo.

Sabemos também que deve haver uma componente dessa onda que se apresenta como um [[Campo Magnético]], para encontrar então esse campo usamos a [[Lei de Faraday]], obtendo:

$$
 \frac{\partial \vec H}{\partial t} = -\frac{(\nabla \times \vec E)}{\mu_0}
$$

Avaliando o [[Rotacional]] do nosso exemplo, obtemos, como $\frac{\partial }{\partial y}=\frac{\partial }{\partial x} = 0$:

$$
\nabla \times \vec E = \frac{\partial E_y}{\partial x}\hat z
$$

Então:

$$
 \frac{\partial \vec H}{\partial t} = \frac{\partial E_y}{\partial x}\hat z
$$

Portanto, utilizando  a [[Regra da cadeia para funções de mais de uma variável]] para substituir a [[Derivadas parciais|derivada parcial]] em $x$ por uma derivada parcial em $t$ e integrando ao longo do tempo, obtemos:

$$
\vec H(x,t) = \frac{E_y(x-ct)}{c\mu_0}\hat k = \sqrt{\frac {\varepsilon_0} {\mu_0}}E_y(x-ct)\hat k = \hat x \times\frac {\vec E(x,t)}{\eta_0}
$$

Ou seja nessa onda, o campo magnético tem magnitude proporcional a magnitude do campo elétrico por uma constante de proporcionalidade $1/\eta_0$ onde $\eta_0$ é a chamada **[[Impedância]] característica do vácuo** e tem o valor de aproximadamente $377 \ \ohm$, ou seja, para uma onda uniforme se propagando no vácuo:

$$
\frac {|\vec E|}{|\vec H|} = \eta_0 = \sqrt{\frac {\varepsilon_0} {\mu_0}} \approx 377 \ \ohm
$$

Como as equações de Maxwell quanto a intensidade de campo são lineares, qualquer superposição de ondas eletromagnéticas continua sendo uma solução da equação de ondas eletromagnéticas.