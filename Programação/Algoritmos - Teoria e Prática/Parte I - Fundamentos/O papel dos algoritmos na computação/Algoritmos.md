De maneira informal, um algoritmo consiste em qualquer procedimento computacional bem definido que toma algum valor ou conjunto de valores como **entrada** e produz algum valor ou conjunto de valores como **saída**, uma sequência de etapas computacionais que que transforma a entrada na saída, além disso, podemos também pensar num algoritmo como uma ferramenta para resolver um **problema computacional** bem especificado onde o enunciado determina a relação desejada entre entrada e saída.

Por exemplo, um problema de ordenação, muito importante por ser uma etapa intermediária para vários outros algoritmos envolve a ordenação de uma sequência de $n$ números em ordem crescente, nesse caso, definindo formalmente:

**Problema de ordenação:**
**Entrada:** Uma sequência de $n$ números $\langle a_1, a_2, a_3, \cdots,  a_n\rangle$
**Saída:** Uma permutação $\langle a_1^\prime, a_2^\prime, a_3^\prime, \cdots,  a_n^\prime\rangle$ da sequência de entrada de modo que os valores satisfaçam $a_1^\prime \leq a_2^\prime \leq \cdots \leq  a_n^\prime$

Nesse sentido, dada uma sequência de números qualquer, como $\langle 12, 23, 112, 93\rangle$, chamada de **instância de entrada** uma vez que trata-se de uma entrada que satisfaz as condições definidas pelo enunciado, um **algoritmo de ordenação correto** (Diz-se que um algoritmo é correto se, para toda instância de entrada, ele parar com a saída correta) retorna como saída a sequência $\langle 12, 23, 93, 112\rangle$ e portando diz-se que ele **resolve** o problema computacional dado.

Por incrível que pareça, em alguns casos, mesmo algoritmos incorretos são úteis, desde que possamos controlar a taxa de erros associados a eles.

Em geral, os algoritmos são usados para resolver muitos problemas diferentes, alguns dos quais tem amplas aplicações e impactos no nosso dia a dia, poderíamos passar horas descrevendo vários desses problemas, porém, a maioria dos problemas algorítmicos interessantes exibem duas características:

1. Têm muitas soluções candidatas a maioria das quais não resolve o problema e encontrar uma solução que funcione ou "a melhor" das soluções pode ser complicado
2. Têm aplicações práticas

No contexto dos algoritmos, entramos num outro tópico importante que também será trabalhado: **Estruturas de dados**, que consistem basicamente num modo de armazenar e organizar dados com o objetivo de facilitar acessos e modificações, como não existem uma só dessas estruturas que seja melhor em todas as situações, é importante trabalhar nosso conhecimento sobre elas destacando seus pontos fortes e limitações.

Embora muito do estudo sobre algoritmos seja sobre entender como os algoritmos clássicos funcionam e que problemas eles resolvem existem uma ampla gama de técnicas que nos darão background para ocasionalmente partir do entendimento de um problema para uma solução algorítmica única para ele, algumas técnicas são Dividir e conquistar, programação dinâmica e análise amortizada.

Uma classe muito interessante de problemas são os chamados NP-Completos, problemas para os quais não se conhece até hoje nenhuma solução eficiente (Uma solução de complexidade polinomial), apesar disso, não há prova matemática de que essa solução eficiente não existe o que deixa uma lacuna, ademais, se um único dos problemas dessa classe tiver uma solução desse tipo isso implica que todos devem ter, um exemplo é o "problema do caixeiro viajante" que consiste em descobrir a rota mais curta possível que visita um conjunto de cidades (exatamente uma vez cada) e retorna ao ponto de partida.

# Exercícios:

1. **Cite um exemplo real que exija ordenação ou um exemplo real que exija o cálculo de uma envoltória convexa.**
	*R: Organizar um fichário em ordem de notas ou encontrar uma forma de cercar um terreno com a menor cerca possível.*
	
2. **Além da velocidade, que outras medidas de eficiência poderiam ser usadas em uma configuração real?**
	*R: Quantidade de armazenamento utilizado na execução, quantidade de energia gasta, banda de rede gasta, entre outros.*
	
3. **Selecione uma estrutura de dados que você já tenha visto antes e discuta seus pontos fortes e suas limitações.**
	*R: Filas: se destaca por sua simplicidade e eficiência de acesso aos últimos índices mas tem como desvantagem a dificuldade para acessar índices intermediários*
	
4. **Em que aspectos os problemas anteriores do caminho mais curto e do caixeiro-viajante são semelhantes? Em que aspectos eles são diferentes?**
	*R: No do caminho mais curto você não precisa retornar ao ponto de partida e não há a restrição de passar apenas uma vez por cada ponto enquanto em ambos o objetivo principal é encontrar uma rota que minimize um custo, tempo ou distância.*
	
5. **Mostre um problema real no qual apenas a melhor solução servirá. Em seguida, apresente um problema em que baste uma solução que seja “aproximadamente” a melhor**