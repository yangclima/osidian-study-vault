O problema da Netflix, consiste em completar lacunas em uma [[Matrizes|matriz]], o seja, encontrar soluções para entradas desconhecidas de uma matriz $A$ utilizando como base para isso a ideia de que essa matriz deve ter o menor [[Escalonamento de matrizes#Posto e Nulidade de uma matriz|posto]] possível, ou seja, manipulando entradas desconhecidas de um matriz, devemos ser capazes de escrever o máximo possível de linhas dessa matriz como combinações  de outras linhas.

Esse procedimento é utilizado em diversos âmbitos para prever dados probabilisticamente, no caso da Netflix a previsão é a respeito da preferência por determinados filmes no catálogo e a ideia é completar e gerar previsões para entradas desconhecidas, ou seja, a partir de poucas entradas conhecidas prever o comportamento provável de uma entrada desconhecida.

O procedimento para isso envolve o [[Escalonamento de matrizes|escalonamento]] da matriz mantendo as entradas desconhecidas como incógnitas e depois encontrando os valores para elas de tal forma que o valor do posto seja minimizado.

