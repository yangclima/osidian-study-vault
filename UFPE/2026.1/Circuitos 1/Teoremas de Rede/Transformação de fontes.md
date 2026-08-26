Vimos que ao aplicar os métodos de [[Análise Nodal]] e [[Análise de malha]] é muito simples de trabalhar com sistemas que tem apenas [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|fontes de tensão]] ou apenas fontes de corrente, já que nesse caso podemos, por inspeção, montar os [[Sistemas lineares]] para resolução do circuito, desse modo, seria muito útil que houvesse um modo de transformar fontes de tensão em fontes de corrente e vice-versa.

E de fato existe um modo de fazer isso: através dos teoremas de [[Teorema de Thévenin|Thévenin]] e [[Teorema de Norton|Norton]], isto é, quando tivermos uma fonte de tensão em série com uma [[Resistores Lineares|resistência]] podemos transformá-la em uma fonte de corrente em paralelo com um resistor e o inverso é verdadeiro, isso usando a relação:

$$V_{oc} = I_{sc}R_{th}$$

De modo que:

1. Se tivermos uma fonte de tensão $V$ em série com uma resistência $R$, podemos substituí-la por uma fonte de corrente $I = V/R$ apontando da direção do polo positivo da fonte de tensão em paralelo com um resistor de resistência $R$.
2. Se tivermos uma fonte de corrente $I$ em paralelo com uma resistência $R$, podemos substituí-la por uma fonte de tensão $V = RI$ com o polo positivo na mesma direção que apontava a fonte de corrente em série com o mesmo resistor $R$.