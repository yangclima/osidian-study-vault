---
next: "[[Método Intuitivo de Análise de Circuitos]]"
prev: "[[Método Básico de Análise de Circuitos]]"
---
Dois tipos de circuito muito comuns e que tomaremos como primitivas no nosso estudo a respeito de circuitos, visto que estes aparecem na construção de outros circuitos mais complexos são os circuitos **Divisores de [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|Tensão]]** e os circuitos **Divisores de [[Corrente]]**.

# Divisores de Tensão
O circuito **divisor de tensão** é formado por uma [[Baterias|fonte de tensão]] conectada a dois ou mais [[Resistores Lineares]] em série a exemplo do seguinte:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_2$] (3,0)
to[R=$R_1$] (3,3) -- (0,3);

\end{circuitikz}
\end{document}
```

Usando o [[Método Básico de Análise de Circuitos]] podemos obter a queda de tensão ao longo do resistor $R_2$ como sendo:

$$
v_1 = \dfrac{R_2}{R_1 + R_2}V
$$

Note então que se considerarmos $V$ como uma tensão de entrada e $V_{R_2}$, a tensão ao longo do resistor $R_2$ como uma tensão de saída, então, temos um circuito que divide a tensão $V$ por um fator $R_2/(R_1+R_2)$ que pode ser ajustado qualquer valor entre $0$ e $1$ alterando o valor das resistências $R_1$ e $R_2$, um circuito ainda mais geral que esse pode ser feito usando vários resistores e fornecendo diferentes valores de tensão de saída simultaneamente.

# Divisores de Corrente
Da mesma maneira que o circuito divisor de tensão divide a tensão de entrada por um determinado fator, podemos construir  um circuito que divide a corrente de entrada por um outro valor utilizando resistores em paralelo a exemplo do seguinte circuito:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[isource, i<=$I$, invert] 
(0,0) -- (3,0)
to[R=$R_1$] (3,3) -- (0,3);

\draw
(3,0) -- 
(6,0) to[R=$R_2$] 
(6,3) -- (3,3);

\end{circuitikz}
\end{document}
```

Analisando esse circuito, podemos obter a corrente $i_1$ no resistor $R_1$ como sendo:

$$
i_1 = \dfrac{R_2}{R_2 + R_1}I
$$

Assim, considerando essa corrente como a corrente de saída, sabemos que a corrente de entrada $I$ é dividida por um fator $R_2/(R_2+R_1)$ que pode ser ajustado através do valor das resistências.