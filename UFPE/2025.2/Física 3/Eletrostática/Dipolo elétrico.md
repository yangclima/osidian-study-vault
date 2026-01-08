---
tags:
  - anky
---
No universo, raramente encontramos [[Carga|partículas carregadas]] livres, já que a [[Lei de Coulomb|Força eletrostática]] atua rapidamente sobre pares dessas partículas unindo-as e formando objetos neutros, nesse sentido, se torna essencial para a compreensão do universo estudar o comportamento de objetos neutros.

O tipo mais simples de objeto neutro é um DIPOLO ELÉTRICO formado por duas partículas de cargas opostas e separadas por uma distância $2a$:

![[fg3_003.png|center]]

Para entender melhor esses objetos, definimos uma medida chamada momento de dipolo ($\vec{p}$) que mede a força do dipolo ou a separação efetiva entre cargas positivas e negativas no sistema. Para um sistema simples como o da imagem acima, definimos:
$$
\vec{p} = q\cdot \vec{d} = 2qa \ \hat{j} \implies |\vec{p}| = 2qa
$$
Isso vale para qualquer par de partículas de cargas iguais e opostas, entretanto, também podemos calcular o momento de dipolo para qualquer conjunto de $n$ partículas cuja soma total das cargas seja $0$, valendo a seguinte relação:
$$
\vec{p} = \sum_{i=1}^n q_i \vec{r}_i
$$
Onde $\vec{r}_i$ é o vetor posição da carga $q_i$, é importante considerar que o momento de dipolo é igual independente da origem utilizada para definir os vetores posição das  

Sobre efeito de um [[Campo Elétrico|campo elétrico]], perceba que a interação das partículas com este campo irá resultar em forças eletrostáticas sobre estas partículas, para um campo elétrico uniforme $\vec{E} = E \  \hat{i}$, o sistemas pode ser ilustrado da seguinte forma:

![[fg3_004.png|center]]


Perceba que as componentes das forças eletrostáticas que atuam na direção do momento de dipolo se cancelam, porém, as componentes ortogonais a $\vec{p}$ não, o que irá gerar um torque $\vec{\tau}$ negativo (Para dentro da folha), ou seja, o dipolo irá passar por um movimento rotacional no sentido horário devido a atuação desse campo.

O vetor $\vec{\tau}$ pode ser obtido pela seguinte relação:
$$
\vec{\tau} = \vec{p} \times \vec{E} \implies |\vec{\tau}| = |\vec{p}|\cdot|\vec{E}| \cdot \sin{(\theta)} = dqE \sin{\theta}
$$
Onde $\theta$ é o ângulo que o vetor $\vec{p}$ faz com o vetor $\vec{E}$.

Inferimos dessa forma, que para um dipolo simples sob efeito de um campo elétrico uniforme, não haverá força resultante, mas pode haver um torque resultante. Para campos elétricos não uniformes, pode haver também força resultante, ocasionando um movimento do dipolo que pode misturar rotação e translação.