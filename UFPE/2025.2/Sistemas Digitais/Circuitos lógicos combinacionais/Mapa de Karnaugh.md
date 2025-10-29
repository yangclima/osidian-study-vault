O mapa de Karnaugh, ou simplesmente mapa K é uma alternativa mais metódica e algorítmica à [[Simplificação Algébrica]],  a ideia é criar uma visualização em forma de tabela que permite encontrar mais facilmente a forma simplificada de uma [[Descrevendo Circuitos Lógicos Algebricamente|expressão algébrica]] ao [[Projetando Circuitos Lógicos Combinacionais|projetar um circuito lógico combinacional]] a partir de uma tabela-verdade. Esse método, entretanto, só é prático ao lidar com, no máximo, 5 ou 6 variáveis, isto utilizando métodos computacionais para auxiliar, manualmente é muito difícil lidar com mais que $4$variáveis.

O método pode ser dividido em alguns passos simples:

1. Montar a tabela com as variáveis envolvidas no problema e preenchê-la de acordo com as informações da tabela-verdade
2. Analise o mapa e encontre os 1s que não são adjacentes a nenhum outro (Isolados)
3. Analise o mapa e encontre os 1s que são adjacentes a apenas outro 1 (Pares)
4. Agrupe qualquer octeto, mesmo que contenha alguns 1s que já tenham sido agrupados
5. Agrupe qualquer quarteto que contenha um ou mais 1s que ainda não tenham sido agrupados, certificando-se de usar o menor número de agrupamentos.
6. Agrupe quaisquer pares necessários para incluir 1s que ainda não tenham sido agrupados, certificando-se de usar o menor número de agrupamentos.
7. Forme a soma OR de todos os termos gerados por cada grupo.

Em alguns casos, ao projetar um circuito existirão certas combinações de valores para as variáveis que não nos interessam, nesse caso, ao invés de preencher o mapa K com 0 ou 1, utilizamos o $x$,  denominado **don't care** e o nosso objetivo passa a ser encontrar valores para esses $x$ tal que tenhamos o menor número de agrupamentos possível.