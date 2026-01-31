---
prev: "[[Convenção de Variáveis Associadas]]"
next: "[[Lei de Elemento]]"
---
Como vimos, o objetivo da [[Abstração de Circuitos]] é modelar os fenômenos físicos utilizando apenas elementos de um conjunto de componentes ideais, para alcançar esse objetivo é essencial que possamos representar os seguintes processos básicos realizados pelos circuitos em termos da nossa abstração:

1. Fontes de Energia
2. Fluxo de energia no circuito
3. Perda de energia
4. Controle do fluxo de energia através de uma força externa
5. Armazenamento de energia

# Fontes Ideais de Tensão e Corrente
As fontes de energia, isto é, as [[Baterias]], podem ser representadas pelas **fontes ideais de [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]]** ou de **[[Corrente|corrente]]**.

A fonte de tensão dependentes são aquelas que fornecem uma tensão variável no tempo e as independentes são as que fornecem uma tensão constante no tempo, representadas por:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]
  \draw (0,3) to[vsource, v=$V(t)$, o-o] (0,0);
  \draw (3,3) to[vsource, v=$V$, o-o] (3,0);
\end{circuitikz}
\end{document}
```

Existe também um elemento ideal que fornece um fluxo de corrente constante e é representado por:


```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]
  \draw (0,3) to[isource, l=$i$, o-o] (0,0);
\end{circuitikz}
\end{document}
```

# Fios ideais 
Na [[Abstração de Circuitos]] usamos o fluxo de energia no circuito é representado através de condutores ideias que não oferecem [[Resistência]] a passagem da corrente e por onde os sinais passam de maneira instantânea, sem atraso de propagação.

# Resistores Ideais
Os [[Resistores Lineares]] e assim, a perda de energia no circuito podem ser abstraídos pelos **Resistores ideais**, resistores que apresentam relações algébricas concretas e previsíveis entre a sua tensão, resistência e corrente, sua representação é:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]
  \draw (0,3) to[R, l=$R$, o-o] (0,0);
\end{circuitikz}
\end{document}
```

# Modelando fenômenos
Note que a ideia é utilizar esses elementos em conjunto para simular as propriedades de circuitos reais, por exemplo, um fio real, que possui uma resistência a passagem de corrente pode ser abstraído como um fio ideal em série com um resistor ideal, da mesma maneira, uma bateria que possui resistência interna e descarrega por ser modelada como uma fonte de tensão dependente em série com um resistor.