Já sabemos que uma [[Conceitos de Probabilidade|Função probabilidade]] é uma função que associa cada evento de um espaço amostral a sua probabilidade, entretanto, para que uma função qualquer possa ser considerada uma função probabilidade ele precisa atingir uma série de requisitos, assim requerendo uma definição mais cuidadosa:

Para um espaço amostral discreto $\Omega$ uma função probabilidade é uma função $P$ que associa cada resultado $\omega$ a um número $P(\omega)$ chamado "Probabilidade de $\omega$". A função $P$ deve satisfazer as seguintes regras:

1. A probabilidade de um resultado qualquer $\omega$ deve estar entre $0$ e $1$, ou seja: $0 \leq P(\omega) \leq 1$.
2. A soma das probabilidades de todos os resultados possíveis deve ser igual a $1$, ou seja, se $\Omega$ tem $n$ resultados possíveis então $\sum_{i=1}^n P(\omega_i) = 1$.

Definida a função $P$ a probabilidade de um evento $E$ é dada então pela soma das probabilidades de cada resultado pertencente a $E$, ou seja:

$$
P(E) = \sum_{\omega \in E} P(\omega)
$$

Além disso, algumas propriedades da função probabilidade podem ser obtidas a partir do que sabemos sobre [[Conjuntos e Notações|conjuntos]].

1. $P(A^c) = 1 - P(A)$
2. Se os eventos $A$ e $B$ são disjuntos, então $P(A \cup B) = P(A) + P(B)$
3. Se os eventos $A$ e $B$ não são disjuntos, então vale a seguinte propriedade de que $P(A \cup B) = P(A) + P(B) - P(A \cap B)$