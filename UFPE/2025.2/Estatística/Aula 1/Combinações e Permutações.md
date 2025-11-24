Dado um [[Conjuntos e Notações|conjunto]] $S$, as vezes queremos ser capazes de mensurar e quantificar a quantidade de formas nas quais podemos selecionar ou ordenar os elementos desse conjunto, nesse sentido, temos duas formas distintas de realizar essas seleções: As **Permutações** e as **Combinações**.

Uma Permutação de um conjunto é uma ordenação particular desse conjunto. Por exemplo, o conjunto $S = \{a,b,c\}$ pode ser organizado de $6$ maneiras: $abc$, $acb$, $bac$, $bca$, $cab$ e $cba$. Usando a [[Princípios de Contagem|regra do produto]] podemos encontrar uma regra para calcular a quantidade de permutações de um conjunto de $k$ elementos, nesse caso, obteremos o seguinte valor:

$$
k! = k\cdot(n-1)\cdot(n-2)\cdots3\cdot2\cdot1
$$

Além disso, podemos também pensar na quantidade de permutações possíveis de $k$ elementos de um conjunto de $n$ elementos (Algumas vezes chamamos esse tipo de permutação pelo nome de "Arranjo"), nesse caso, denotamos (Lê-se "Permutação de $n$ elementos tomados $k$ a $k$):

$$
{}_nP_k = \dfrac{n!}{(n-k)!}
$$

Por sua vez, uma Combinação $k$ elementos de um conjunto $S$ pode ser entendida como a quantidade de subconjuntos distintos de $k$ elementos que podemos formar com os $n$ elementos de $S$, ou seja, em contraste com a permutação, aqui a ordem não importa, as combinações de $n$ elementos tomados $k$ a $k$ é dada por:

$$
{}_nC_k = \binom{n}{k} = \dfrac{n!}{k!(n-k)!} = \dfrac{{}_nP_k}{k!}
$$