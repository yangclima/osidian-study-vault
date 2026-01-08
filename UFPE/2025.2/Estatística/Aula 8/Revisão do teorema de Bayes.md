Mesmo tentando, não conseguimos deixar claro o suficiente o quanto o [[Teorema de Bayes]] é essencial para a [[Introdução a Estatística|estatística]] inferencial. Porém, podemos deixar clara sua utilidade da seguinte maneira: 

Digamos que a partir de um experimento bem planejado, coletamos um conjunto de dados $D$ a partir do qual, inferimos uma hipótese $H$, assumindo o evento $H$ como "A hipótese inferida é verdadeira" e o evento $D$ como "Os dados são reais", pelo teorema de Bayes, temos:

$$
P(H|D) = \dfrac{P(D|H)\cdot P(H)}{P(D)}
$$

Assim, perceba que $P(H|D)$ é a probabilidade da nossa hipótese ser verdadeira e portanto refletir a realidade, o que nos permite chegar a conclusões satisfatoriamente prováveis sobre um fenômeno ou mecanismo a partir da coleta de dados sobre estes, basta que conheçamos todos os elementos que estão no lado esquerdo da equação.

Infelizmente, na grande maioria dos casos, não conhecemos com precisão todos esses elementos, assim, a chave é então desenvolver métodos que nos permitam lidar com essa falta de conhecimento e nos permitam então fazer boas inferências. 