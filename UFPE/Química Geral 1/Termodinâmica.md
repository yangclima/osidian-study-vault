---
aula: 1
---
O principal conteúdo da primeira unidade de Química Geral 1 é a Termodinâmica, que, de forma simplificada, consiste no estudo da transformação e transferência de energia, o primeiro passo para compreender esse campo de estudo é aprender a dividir o universo conforme o nosso interesse utilizando o conceito de sistema.
# Sistemas
Resolver problemas químicos seria basicamente impossível se precisássemos sempre considerar o universo inteiro nos nosso cálculos, por isso, dividimos o universo em duas partes: O Sistema e a vizinhança. 

**O Sistema** é a parte que nos interessa, uma parte limitada do universo na qual queremos analisar ou até predizer os efeitos ou consequências de algo, já a **Vizinhança** representa todo o restante do universo que não nos interessa a não ser pela seus efeitos no nosso sistema. 
$$
\text{Sistema} + \text{Vizinhança} = \text{Universo}
$$
## Tipos de sistema 
Existem 3 tipos principais de sistema:
- Aberto: Troca massa e energia com a vizinhança 
- Fechado Troca apenas energia com a vizinhança
- Isolado: Não troca nada com a vizinhança
# Trabalho 
O trabalho é o principal conceito da termodinâmica, é nele que estamos interessados, é ele que queremos gerar. Trabalho consiste basicamente no movimento executado contra uma força oposta, normalmente é denotado por $w$ e medido em Joules ($J$) que equivale a $1 Kg \cdot m² s^{-2}$ e pode ser calculado por:
$$
w = \int F dx
$$
$$
w = \int^{V_f}_{V_i} P dv
$$
Outra unidade de medida para o trabalho é o $atm \cdot l$ que é equivalente a $101,325 J$.
# A energia interna
A energia interna $U$ é medida do conteúdo total de energia de um sistema, ou seja, sua capacidade de gerar trabalho, porém, como a energia está relacionada com o estado energético de cada átomo do sistema, é muito difícil mensurar a energia interna através de um estado do sistema, por isso, é mais comum mensurar a variação de energia interna $\Delta U$.

Se a única forma de transferência de energia ocorrendo for o trabalho, então:
$$
\Delta U = w
$$
# Trabalho de expansão
O trabalho pode ser dividido em dois tipos: Trabalho de expansão e trabalho de não expansão, e os nomes já dizem tudo, o principal objeto de interesse na termodinâmica é o trabalho de expansão, ou seja, o trabalho envolvendo variação de volume e esse pode ser dividido em dois tipos
## Expansão isobárica
A expansão isobárica se refere a expansão que acontece sob pressão constante, como o gás se expandindo dentro de um cilindro coma pressão externa constante, nesse caso o trabalho é dado por:
$$
w = P_{ext} \Delta v

$$
## Expansão isotérmica reversível
A expansão isotérmica reversível é um processo que pode ser revertido por uma mudança infinitesimal em uma variável, ou seja, meio que ocorre em pequenos passos reversíveis, é nesse tipo de expansão que conseguimos extrair o máximo de trabalho do sistema, e esse trabalho  é dado por:
$$
w = nRT\ln{\dfrac{V_2}{V_1}}
$$
# O calor
O calor é a energia transferida em consequência de uma diferença de temperatura, ou seja, a energia em forma de calor que flui de uma região mais quente para uma mais fria, toda forma de variação da energia interna que não ocorrer por meio de trabalho ocorre por meio de transferência de calor, então, se a única forma de transferência de energia ocorrendo for a transferência de calor:
$$
\Delta U = q
$$
A unidade de medida do calor é também o Joule, mas é muito comum medi-lo em calorias, uma caloria ($cal$) equivale a $4,184J$, oura unidade, usada normalmente no contexto alimentar é a Caloria nutricional ($Cal$) que equivale a $1kcal$. 

o processos podem ser classificados com base na perda/ganho de calor pelo sistema que o realizou, se $q < 0$ o processo é **exotérmico** e se $q > 0$ o processo é **endotérmico**.

Por mais que intuitivamente relacionemos calor a temperatura, existem vários processos em que ocorre transferência de calor sem variação de temperatura, porém, uma forma de relacionar o calor á temperatura é através da capacidade calorífica $C$ que é dada por:
$$
C = \dfrac{q}{\Delta T}
$$
A medida acima é útil porém, extensiva e varia de acordo com o tamanho da amostra sendo específica da amostra ou sistema, para generalizar esse valor para uma determinada substância utilizamos a capacidade calorífica específica ($C_s$) e a capacidade calorífica molar ($C_m$) dadas por:
$$
C_s = \dfrac{C}{m}
$$
$$
C_m = \dfrac{C}{n}
$$
# Equilíbrio térmico
Um ponto para se pensar é no equilíbrio térmico, por mais que ter sistema e vizinhança na mesma temperatura nos passe a ideia de que não haverá troca de calor o que corre na verdade é que o calor flui reversivelmente em igual velocidade nas duas direções, mantendo o equilíbrio.
# Primeira lei da termodinâmica
A primeira lei da termodinâmica é a união dos conceitos que vimos até aqui e determina que uma mudança na energia interna só ocorre em função do trabalho ou transferência de calor e que portanto, a **a energia interna de um sistema isolado é constante**.
$$
\Delta U = w + q
$$
