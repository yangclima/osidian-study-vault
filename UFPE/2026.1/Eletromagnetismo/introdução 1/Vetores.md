Alguns fenômenos, situações e objetos físicos não podem ser representados simplesmente por escalares, números, pois estes apresentam direções, sentido, um bom exemplo é a velocidade, a aceleração ou o próprio deslocamento.

Um vetor $\vec A$ tem magnitude e direção. Sua *magnitude* é denotada por $|A|$ ou simplesmente $A$. Um *vetor unitário* $\vec a_A$ ao longo de $\vec A$ é então um vetor cuja magnitude é unitária (Isto é, 1) e que é orientado na mesma direção que $\vec A$, dessa maneira:

$$
\vec a_A = \frac {\vec A}{|A|}
$$

Como $|\vec a_A|$ é 1 podemos então escrever:

$$
\vec A = |A|\cdot\vec a_A 
$$

O que significa que podemos escrever um vetor em termos de sua magnitude e orientação, estendendo isso para o espaço cartesiano, podemos representar um vetor qualquer nesse espaço através de suas coordenadas:

$$
\vec A = (A_x,A_y,A_z) = A_x\vec a_x + A_y\vec a_y + A_z\vec a_z
$$

Onde $A_x$, $A_y$ e $A_z$ são as *componentes* de $A$, nas direções $x$, $y$ e $z$, respectivamente e os vetores $\vec a_x$, $\vec a_y$ e $\vec a_z$ são os vetores unitários em cada uma dessas direções, respectivamente.

E a norma do vetor $A$ pode então ser calculada como:

$$|A| = \sqrt{A_x^2+A_y^2+A_z^2}$$

E o vetor unitário em sua direção é:

$$
\vec a_A = \frac{A_x\vec a_x + A_y\vec a_y + A_z\vec a_z}{\sqrt{A_x^2+A_y^2+A_z^2}}
$$

É possível definir então as operações de soma e multiplicação por escalar de vetores, ambas lineares, comutativas e associativas.

Podemos, tomando por convenção uma origem para o sistema de coordenadas em que estamos trabalhando, definir os vetores posição e distância, o vetor posição $\vec r_p$ é um vetor que aponta da origem até um ponto $P$ e representa a posição desse ponto, por outro lado o vetor distância $\vec r_{PQ}$ representa a distância entre dois pontos $P$ e $Q$ e pode ser obtido através dos vetores posição desses pontos:

$$
\vec r_P = OP = xa_x + ya_y + za_z
$$
$$
\vec r_{PQ} = \vec r_Q - \vec r_P = OP = (x_Q - q_P)a_x + (y_Q - y_P)a_y + (z_Q - z_P)a_z
$$

Depois disso podemos ainda definir o [[Produto interno]], também chamado de produto escalar e o Produto Vetorial também conhecido como Produto Cruzado entre dois vetores.