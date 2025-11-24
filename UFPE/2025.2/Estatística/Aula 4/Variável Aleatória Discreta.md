Seja $\Omega$ um [[Conceitos de Probabilidade|espaço amostral]]. Uma variável aleatória discreta (v.a.d.) é uma função

$$
X: \Omega \rightarrow \mathbb{R}
$$

que associa cada resultado possível $\omega$ do experimento a um número real $X(\omega)$ que assume um conjunto discreto de valores (Valores finitos ou infinitos, mas contáveis). A variável aleatória recebe esse nome por estar associada ao resultado de um experimento aleatório e pelo fato de realizarmos operações aritméticas com o seu valor, quando escrevemos $X=a$, estamos nos referindo ao conjunto de todos os resultados $\omega$ tais que $X(\omega) = 2$.

Por exemplo, dado um experimento constituído pelo lançamento de dois dados, digamos que em um cassino, se os valor da soma dos resultados obtidos nos dois dados for igual $7$, você recebe $R\$ \ 500$, caso contrário, perde $R\$ \ 100$, uma possível variável discreta associada ao nosso experimento pode ser:

$$
X(i, j) = 
\begin{cases} 
500 & \text{se } i + j = 7 \\
-100 & \text{se } i + j \neq 7
\end{cases}
$$

Nesse caso, o evento $X = 500$ é o [[Conjuntos e Notações|conjunto]] (Evento) formado pelos seguintes valores: $\{(1,6), (2,5), (3,4), (4,3), (5,2), (6,1)\}$, ou seja, o conjunto de todos os valores $(i,j)$ tais que $i + j = 7$.

Uma outra forma de estabelecer um evento através de uma variável aleatória é através de uma desigualdade, por exemplo $X \leq a$ é o evento ou conjunto de resultados possíveis $\omega$ tais que $X(\omega) \leq a$.
