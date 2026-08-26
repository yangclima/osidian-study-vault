É agora que acessamos o grande poder dos [[Números Complexos]] na análise de circuitos. Como temos visto anteriormente, os cálculos dos parâmetros em circuitos que possuem [[Capacitores em circuitos|capacitores]] e [[Indutores em Circuitos|indutores]] utilizando [[Fasores]] em regime permanente é de fato muito semelhante ao que fazíamos para circuitos resistivos, matematicamente, são idênticos e por isso, podemos utilizar a [[Análise Nodal]] para resolver circuitos da alta ordem através da aplicação de fasores.

Basicamente nada muda na técnica, exceto por um passo inicial a mais: basicamente começamos a análise transformando as [[Indutores e indutâncias|indutâncias]] e [[Capacitores|capacitâncias]] em seus equivalente complexos:

$$C \to -\dfrac{j}{\omega C} \ \ \ \ \ \text{e} \ \ \ \ \ L \to j\omega L$$

O próximo passo então é simplesmente tomar um dos nós como referência e o restante como tensões incógnitas do nosso problema obtendo para cada nó (com exceção do nó de referência) uma equação nodal que permitirá, através das técnicas de resolução de [[Sistemas lineares]] que já conhecemos, encontrar cada tensão de nó e através delas qualquer [[Potencial elétrico|tensão]] ou [[Corrente]] no circuito.

Vale notar que vale ainda aqui, o método simplificado de resolução de circuitos com fontes de corrente que já conhecemos e também a definição de super-nós.