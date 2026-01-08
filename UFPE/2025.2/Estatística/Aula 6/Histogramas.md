Uma forma muito útil de resumir múltiplas amostras de uma [[Variável Aleatória Contínua|variável aleatória]] é utilizando um tipo de gráfico determinado histograma. Para construir um histograma podemos seguir alguns passos simples:

1. Pegue um intervalo da reta real e divida-o em $m$ intervalor como extremos $b_0,b_1,\cdots,b_m$ de maneira que cada intervalo tenha a mesma largura, ou seja, $(b_m-b_0)/m$.
2. Coloque cada amostra $x_i$ no intervalo que contém o seu valor. Se $x_i$ estiver no limite entre os intervalos, o colocamos no intervalo da esquerda (Lógica que o `R` segue).
3. Para desenhar um **histograma de frequência**, coloque uma barra vertical acima de cada intervalo, a altura da barra em cada intervalo deve ser igual ao número de amostras $x_i$ compatíveis  com o respectivo intervalo.
4. Para desenhar um **histograma de densidade**, coloque uma barra vertical acima de cada intervalo, a área da barra acima de cada intervalo deve ser igual a fração de todos os $x_i$ compatíveis com o respectivo intervalo.

Apesar de ser possível construir histogramas com intervalos de diferentes amplitudes, não é um prática recomendada, já que isso pode acabar por distorcer a visualização dos dados.