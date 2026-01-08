Introduziremos agora uma operação que pode ser feita sobre campos vetoriais e que é semelhante a uma [[Derivada|derivação]], porém, gera um campo vetorial

> Seja um campo vetorial $\vec{F} = P\hat{i} + Q\hat{j} + R\hat{k}$ definido em $\mathbb{R}^3$ para o qual as derivadas parciais de $P$, $Q$ e $R$ existem, definimos o rotacional de $\vec{F}$ como:
> $$\nabla \times \vec{F} = \text{rot} \, \vec{F} = \left(\dfrac{\partial R}{\partial y}-\dfrac{\partial Q}{\partial z}  \right)\hat{i} + \left(\dfrac{\partial P}{\partial z}-\dfrac{\partial R}{\partial x}  \right)\hat{j} + \left(\dfrac{\partial Q}{\partial x}-\dfrac{\partial P}{\partial y}  \right)\hat{k}$$

Podemos encontrar facilmente o rotacional fazendo o [[Uso de vetores na física#Produto vetorial|produto vetorial]] de $\nabla = \left(\dfrac{\partial}{\partial x}, \dfrac{\partial}{\partial y}, \dfrac{\partial}{\partial z}\right)$ e o vetor $\vec F = (P,Q,R)$, obtido resolvendo seguinte determinante:

$$
\nabla \times \mathbf{F} = 
\begin{vmatrix} 
\mathbf{i} & \mathbf{j} & \mathbf{k} \\ 
\frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ 
P & Q & R 
\end{vmatrix} 
$$

Para o caso do rotacional vale a propriedade de que para uma função qualquer $f$ que tem [[Derivadas Parciais de ordem superior]] contínuas, temos que:

$$
\text{rot } {\nabla f} = \nabla \times \nabla f = 0 
$$
Como sabemos que um [[Campos vetoriais|campo vetorial]] $\vec F$ é conservativo se é da forma $\vec F = \nabla f$, chegamos na conclusão de que, se $\vec F$ é conservativo, então seu rotacional é nulo ($\nabla \times \vec F = 0$), em geral, a recíproca não é verdadeira, porém, se $\vec F$ é definido em todo o espaço (O seu domínio é "simplesmente conexo", não apresenta furos) então a recíproca vale e então $\nabla \times \vec F$ implica que $\vec F$ é conservativo.

Uma forma intuitiva de se pensar no rotacional de um campo é pensar em como esse conceito funciona ao lidar com campos vetoriais que representam a velocidade em um fluido, onde o rotacional representa a tendência das partículas girarem em torno do eixo $\nabla \times \vec F$ e o seu módulo representa a velocidade na qual essas partículas se movem em torno de tal eixo.