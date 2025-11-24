A Lei da Probabilidade Total é uma definição da probabilidade que nos permite utilizar a [[Probabilidade Condicional]] através da regra do produto para calcular a probabilidade de eventos mais complexos. 

Essa lei envolve o conceito de **Partição**, dado um [[Conceitos de Probabilidade|espaço amostral]] $\Omega$ (O mesmo vale para um [[Conjuntos e Notações|conjunto]] qualquer $S$) fazer uma partição de $\Omega$ é como quebrá-lo em pedaços menores e disjuntos, dessa forma, um conjunto de eventos $B_1, B_2, B_3, \cdots, B_n$ é tal que a intersecção entre cada $B_k$ é vazia, e a união de todos os eventos $B_k$ resulta em $S$. Ou seja:

1. $B_i \cap B_j = 0, \forall i \neq j$
2. $\bigcup\limits_{i=1}^n = S$

Assim, como os pedaços $B_k$ não se intersectam podemos chegar na probabilidade total de um evento qualquer $A$ calculando separadamente os valores de sua probabilidade condicional com cada pedaço $B_k$:

$$
P(A) = P(A \cap B_1) + P(A \cap B_1) + \cdots + P(A \cap B_n)
$$

Assim, utilizando a regra da multiplicação de probabilidades, temos:

$$
P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + \cdots + P(A|B_n)P(B_n)
$$

Essa definição é chamada de **Lei da probabilidade total**.

Uma excelente dica para trabalhar com a lei da probabilidade total é o uso de **Diagramas de árvore** para encontrar mais intuitivamente a probabilidade de eventos, a ideia é organizar sequencialmente as ideias, cada nível representa os resultados possíveis para um experimento ou uma parte de um e em cada ramo escrevemos a probabilidade do evento representado pelo nó em sua ponta, dessa maneira, a probabilidade de um nó é obtida multiplicando a probabilidade de cada ramo acima dele até chegar no nó superior, por exemplo:

![[est_002.png|center]]

Nesse caso, a probabilidade do evento $R_2$ pode ser obtida somando cada um dos nós representado por $R_2$, assim, temos 

$$
P(R_2) = \dfrac{4}{7}\cdot\dfrac{5}{7} + \dfrac{6}{7}\cdot\dfrac{2}{7}
$$

O diagrama de árvore, nesse caso, não passa de uma representação visual do teorema da probabilidade total.
