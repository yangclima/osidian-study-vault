---
next: "[[Lei de Kirchhoff das Correntes]]"
prev: "[[Representação de sinais]]"
---
Grande parte das redes e sistemas elétricos podem ser modeladas simplesmente como **Redes resistivas**, isto é, redes compostas apenas por [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|Fontes Ideais de Tensão e Corrente]] e [[Componentes Ideais#Resistores Ideais|Resistores]], nosso objetivo é então, desenvolver métodos sistemáticos que nos permitam analisar e resolver circuitos desse tipo, isto é, encontrar a [[Potencial elétrico|tensão]] e a [[Corrente]] em cada elemento do circuito.

Como havíamos definido, se os requisitos para a validade da nossa [[Abstração de Circuitos|Abstração de Circuitos de Parâmetros Agrupados]] forem atendidos, podemos evitar o complexo e dispendioso uso das [[Equações de Maxwell]], utilizando ao invés disso relações algébricas simples para relacionar as variáveis do nosso circuito, o que poderá ser feito através das [[Leis de Kirchhoff]], porém, para a plena compreensão dessas leis precisamos definir bem a nossa terminologia.

Um circuito elétrico é construído conectando múltiplos componentes elétricos através de seus terminais, chamamos então as junções onde os terminais de $2$ ou mais componentes se conectam de **Nós do circuito**, por outro lado, os fios que conectam os nós são denominados **Ramos ou Arestas do circuito**.

Um fato notável, é que, como na nossa abstração, tomamos os fios como sendo ideais, então, para ser considerado um nó, não necessariamente os elementos precisam estar conectados no mesmo ponto do espaço, podendo haver então, os chamados **nós distribuídos**.

![[circ1_001.png|center]]

Assim, de maneira muito óbvia, definimos a **corrente de ramo** como a corrente, unicamente definida, que passa ao longo de um ramo do circuito, e de forma equivalente, a **tensão de ramo** como a diferença de potencial ao longo de um **ramo de circuito**, de modo tal que o potencial elétrico em cada nó do circuito está também univocamente definido.

O último conceito importante é o conceito de **laço do circuito** que se refere a qualquer caminho fechado no circuito, isto é, conjuntos de arestas que começam e terminam no mesmo nó.