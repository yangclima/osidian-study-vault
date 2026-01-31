De maneira análoga a nossa derivação para o [[Teorema de Thévenin]], podemos elaborar o conceito de **Rede equivalente de Norton** usando ao invés de uma [[Corrente|corrente]] de teste, uma [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]] de teste $v_{test}$.

A ideia é a mesma, por exemplo, considere o seguinte circuito:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[V=$V$, invert] (3,3) 
      to[short, i<=$i$] (6,3) 
      to[open, *-*, v=$v$] (6,0) 
      to[R=$R_3$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[I=$I$] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Queremos então decompor a corrente $i$ em duas componentes, uma denotada por $i_a$ e também chamada de **corrente de curto circuit**o $i_{sc}$,  equivalente a corrente entre os terminais medida no circuito original  quando os terminais estão curto circuitados e uma denotada por $i_b$ equivalente a corrente medida entre os terminais sob efeito de uma tensão externa de teste $v_{test}$ e com as fontes internas de tensão e corrente setadas para $0$. 

No caso do nosso circuito, para calcular $i_a$ consideramos o seguinte sub circuito:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[V=$V$, invert] (3,3) 
      to[short, i<=$i$] (6,3) 
      to[short, *-*, v=$v$, i=\large$i_{sc}$] (6,0) 
      to[R=$R_3$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[I=$I$] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Usando o [[Teorema da superposição]], obtemos então 

$$
i_a = -i_{sc}= \dfrac{V + I(R_2 + R_3)}{R_1 + R_2 + R_3}
$$

Por fim, calculamos $i_b$ a partir do seguinte sub circuito:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[short, invert] (3,3) 
      to[short, i<=$i$] (6,3) 
      to[V=$v_{test}$, *-*] (6,0) 
      to[R=$R_3$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[open] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Obtendo então pelo [[Método Intuitivo de Análise de Circuitos]] que 

$$
i_b = \dfrac{v_{test}}{R_{eq}} = \dfrac{v_{test}}{R_1 + R_2 + R_3}
$$

Nesse caso, temos que:

$$
i = i_a + i_b = -i_{sc} + \frac{v_{test}}{R_{eq}} = \dfrac{V + I(R_2 + R_3)}{R_1 + R_2 + R_3} + \dfrac{v_{test}}{R_1 + R_2 + R_3}
$$

Nesse caso, como $v_{test}$ é uma tensão externa a nosso circuito, podemos simplificar esse nosso circuito através da chamada **Corrente equivalente de Norton** $I_N = i_{sc}$ e da **Resistência equivalente de Norton** $R_N = R_{eq}$, ou seja:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[I=$I_n$] (0,3) 
      to[short, invert] (3,3) 
      to[short, i<=$i$] (6,3) 
      to[open, *-*, v=$v$] (6,0) 
      to[short] (3,0) 
      to[short] (0,0);

\draw (3,0) to[R=\large$R_n$] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Os métodos de Thévenin e Norton baseiam-se no mesmo conceito e obtendo seja a tensão de Thévenin ou a corrente de Norton e a Resistência equivalente, podemos obter ambas as abstrações através da relação:

$$
v_{oc} = i_{sc}\cdot R_{eq} \implies V_{th} = I_{n}\cdot R_eq
$$

Assim, sintetizamos o processo de simplificação de circuitos através de uma rede equivalente de Norton em dois passos:

1. Obter $I_n$ medindo ou calculando a corrente de curto circuito nos terminais do circuito original.
2. Obter $R_n$ medindo a resistência equivalente entre os terminais da rede com as fontes de tensão e corrente internas zeradas,

Assim, temos outra poderosa ferramenta da análise de circuitos tendo em vista que que podemos simplificar circuitos lineares enormes através de apenas dois componentes em paralelo.