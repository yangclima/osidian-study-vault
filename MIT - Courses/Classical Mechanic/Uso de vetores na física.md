# Decomposição de Vetores
Na física é muito útil separar os vetores em componentes vetoriais na direção de cada eixo coordenado, nos possibilitando separar os movimentos, forças, velocidades e acelerações em grupos que atuam em uma única direção e assim calcular sua influência um sobre o outro com maior facilidade, esse é o principal objetivo dos [[Vetores#Vetor unitário|vetores unitários]]. Sempre podemos definir um vetor do espaço $xyz$ na forma de uma soma de 3 vetores que apontam cada um na direção de cada vetor unitário do espaço: $\vec{A} = \vec{A_x} + \vec{A_y} + \vec{A_z}$, e cada um desses vetores pode ser escrito como um múltiplo de seu respectivo vetor unitário, ou seja, $\vec{A_x} = A_x \hat{i}$, $\vec{A_y} = A_y \hat{j}$ e $\vec{A_z} = A_z \hat{k}$, dessa forma cada vetor no espaço pode ser decomposto em seus **componentes**:
$$
\vec{A} = A_x \ \hat{i} + A_y \ \hat{j} + A_z \ \hat{k}
$$
# Magnitude de um vetor
Para calcularmos a magnitude de um vetor utilizamos a seguinte relação:
$$
|\vec{A}| = \sqrt{A_{x}^{2} + A_{y}^{2} + A_{z}^{2}}
$$
# Direção
Algumas vezes, não conhecemos os componentes de um vetor, mas sim o seu ângulo comum determinado referencial, normalmente o eixo $x$, dessa forma, podemos denotar o vetor da seguinte maneira:
$$
\vec{A} = |\vec{A}|\cos{(\theta)} \ \hat{i} + |\vec{A}|\sin{(\theta)} \ \hat{j} 
$$
ou seja, o componente $A_x$ de $\vec{A}$ é $|\vec{A}|\cos{(\theta)}$ e seu componente $A_y$ é  $|\vec{A}|\sin{(\theta)}$, da mesma maneira, conhecendo previamente os componentes de $\vec{A}$, podemos expressar seu ângulo com o eixo $x$ positivo através de:
$$
\dfrac{A_y}{A_x} = \dfrac{|\vec{A}|\sin{(\theta)}}{|\vec{A}|\cos{(\theta)}} = \tan{\theta} \implies \theta = \tan^{-1}{(\dfrac{A_y}{A_x})}
$$
# Vetores unitários
Usando a notação da decomposição de vetores, podemos definir o [[Vetores#Vetor unitário|vetor unitário]]. na direção de um vetor $\vec{A}$ qualquer através da expressão:
$$
\hat{A} = \dfrac{\vec{A}}{|\vec{A}|} = \dfrac{A_x \ \hat{i} + A_y \ \hat{j} + A_z \ \hat{k}}{\sqrt{A_{x}^{2} + A_{y}^{2} + A_{z}^{2}}}
$$
# Transformação de vetores em sistemas de coordenadas rotacionados
Em alguns problemas nós precisamos lidar com referenciais diferentes, ou seja, sistema de coordenadas que estão deslocados em relação ao outro, ou rotacionados, para isso, precisamos ser capazes de transformar os vetores de um sistema rotacionados para representá-los no sistema canônico, para isso precisamos transformar os nossos vetores unitários e nossa coordenadas:
$$
\begin{cases}
\hat{i}^{\prime} = \cos{(\theta)} \hat{i} + \sin{(\theta)} \hat{j} \\
\hat{j}^{\prime} = - \sin{(\theta)} \hat{i} + \cos{(\theta)} \hat{j}  
\end{cases}
\ \ \ \ \text{e} \ \ \ \
\begin{cases}
A_x^\prime = A_x\cos{(\theta)} + A_y\sin{(\theta)}\\
A_y^\prime = - A_x\cos{(\theta)} + A_y\cos{(\theta)} 
\end{cases}
$$
Dessa forma, para transformar um vetor canônico em um vetor do sistema cartesiano canônico usamos:
$$
x \ \hat{i} + y \ \hat{j} = (x \cos{(\theta)} + y \sin{(\theta)}) \ \hat{i}^{\prime} + (-x \sin{(\theta)} + y \cos{(\theta)}) \ \hat{j}^{\prime}
$$
E para fazer a operação inversa:
$$
x^\prime \ \hat{i}^{\prime} + y^\prime \ \hat{j}^{\prime} = (x^\prime \cos{(\theta)} - y^\prime \sin{(\theta)}) \ \hat{i} + (x^\prime \sin{(\theta)} + y^\prime \cos{(\theta)}) \ \hat{j}
$$
# Produto vetorial
$$
\vec{A} \times \vec{B} = |\vec{A}||\vec{B}|\sin{\theta}\hat{n}
$$O produto vetorial é um operação definida entre dois vetores e que retorna um terceiro vetor, sendo este, um vetor normal ao plano formado pelo dois vetores (operandos), sendo assim, existem duas possibilidades para esse vetor, apontando para cima ou para baixo, essa propriedade é definida através da **regra da mão direita**. É possível interpretar geometricamente o produto vetorial como  a área do paralelogramo formado pelos dois vetores. O produto vetorial possui as seguintes propriedades:
1. Magnitude: $|\vec{A} \times \vec{B}| = |\vec{A}||\vec{B}|\sin{\theta}$
2. Não-comutatividade: $\vec{A} \times \vec{B} = -(\vec{B} \times \vec{A}$)
3. Distributividade da multiplicação de um escalar sobre um vetor sobre o produto vetorial: $c(\vec{A} \times \vec{B}) = c\vec{A} \times c\vec{B}$
4. Distributividade sobre a soma de vetores: $\vec{A} \times (\vec{C} + \vec{B}) = (\vec{A} \times \vec{B}) + (\vec{A} \times \vec{C})$
Seja $\vec{A} = (A_x, A_y, A_z)$ and $\vec{B} = (B_x, B_y, B_z)$ então o produto vetorial $\vec{A} \times \vec{B}$ é definido por:
$$
\begin{vmatrix}
\hat{i} & \hat{j} & \hat`{k}\\
a_1 & a_2 & a_3\\
b_1 & b_2 & b_3
\end{vmatrix} 
= 
(A_yB_z-A_zB_y)\hat{i} + (A_zB_x-A_xB_z)\hat{j}+(A_xB_y-A_yB_x)\hat{k}
$$
O vetor unitário normal pode ser dado por:
$$
\hat{n} = \pm \dfrac{\vec{A} \times \vec{B}}{|\vec{A} \times \vec{B}|}
$$
# Produto escalar vetorial
$$
\vec{A} \cdot \vec{B} = |\vec{A}||\vec{B}|\cos{\theta}
$$
O produto escalar vetorial é um operação realizada entre dois vetores que retorna sempre um escalar, ou seja, um número real, que pode ser interpretado geometricamente como o módulo da projeção ortogonal de um vetor sob outro.
1. $A_x \ \hat{i} + A_y \ \hat{j} + A_z \ \hat{k} \cdot B_x \ \hat{i} + B_y \ \hat{j} + B_z \ \hat{k} = A_xB_x + A_yB_y + A_zB_z$
2. Comutatividade: $\vec{A} \cdot \vec{B} = \vec{B} \cdot \vec{A}$
3. Distributividade do produto de um escalar sobre um vetor sobre o produto escalar vetorial: $c(\vec{A} \cdot \vec{B}) = c\vec{A} \cdot \vec{B}$
4. Distributividade sobre a soma de vetores: $\vec{A} \cdot (\vec{B} + \vec{C}) = \vec{A} \cdot \vec{B} + \vec{A} \cdot \vec{C}$
5. $\vec{A} \cdot \vec{B} = 0$ somente se os vetores forem perpendiculares
