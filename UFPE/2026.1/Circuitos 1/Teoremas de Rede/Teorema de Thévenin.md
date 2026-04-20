Agora, munidos do [[UFPE/2026.1/Circuitos 1/Teoremas de Rede/Teorema da superposição]] podemos criar uma espécie de evolução do nosso [[Método Intuitivo de Análise de Circuitos]], isto é, um método de simplificação de circuitos que nos permitirá suprimir uma série de detalhes e focar apenas na parte do circuito que nos interessa.

A ideia aqui é olhar o circuito a partir de um par de terminais, o que é ideal até mesmo para as nossas ideias de [[Abstração e Modularidade]] como a [[Abstração de Circuitos]], e mostraremos que devido a linearidade dos sistemas podemos representar qualquer conjunto complexo de [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|fontes de tensão, fontes de corrente]] e [[Resistores Lineares]] por uma fonte de tensão em série com um resistor.

A ideia aqui é resumir, simplificar os circuitos a partir  da noção de que a tensão e a corrente entre dois nós dependem linearmente dos componentes e suas contribuições avaliadas independentes podem ser simplesmente somadas, assim, dado um circuito como o seguinte:

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

Então, a ideia é simplificar esse circuito a partir da ideia dele visto dos seus terminais, isto é, considerando $i$ a corrente entre os terminais e $v$ a tensão entre eles, essa tensão pode então ser decomposta em $v_a$, uma tensão independente das fontes internas do circuito e representa a queda de tensão causada pela corrente $i$ fluindo pelos componentes internos e $v_b$ a contribuição para a tensão proveniente dessas fontes, assim $v = v_a + v_b$.

O próximo passo é então calcular essas componentes da tensão:

Primeiro, $v_a$ pode ser calculada aplicando uma corrente $i_{test}$ aos terminais considerando que todas as fontes internas são iguais a $0$, no caso do nosso exemplo, teríamos: 

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[short, invert] (3,3) 
      to[short, i<=\large $i_{test}$] (6,3) 
      to[I, invert, *-*, v>=$v$] (6,0) 
      to[R=$R_3$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[open] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Nesse caso, devido ao curto-circuito sabemos, por análise visual que a tensão entre os terminais é $v_a = i_{test}R_{eq}$ e que $R_{eq} = R_1 + R_2 + R_3$.

Para $v_b$ também chamada de tensão de circuito aberto $v_{OC}$ consideramos então os valores originais das fontes no circuito:

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

Usando [[Análise Nodal]] obtemos então que $v_b = v_{oc} = V + I(R_1 + R_2)$.

Por fim, sabemos então que $v$ no circuito original pode então ser calculada como sendo:

$$
v = v_a + v_b = i_{test}R_{eq} + v_{oc} = i_{test}( R_1 + R_2 + R_3) +  V + I(R_1 + R_2)
$$ 
Como então a corrente $i_{test}$ é uma corrente qualquer, externa ao circuito, podemos então simplificar o nosso circuito como sendo:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=\large$R_{eq}$] (0,3) 
      to[V=\large$v_{oc}$, invert] (3,3) 
      to[short, i<=$i$] (6,3) 
      to[open, *-*, v=$v$] (6,0) 
      to[short] (3,0) 
      to[short] (0,0);

\draw (3,0) to[open] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Chamamos então $R_{eq}$ de **Resistência equivalente de Thévenin** e $v_{oc}$ de **Tensão equivalente de Thévenin**, dessa maneira, abstraímos o circuito complexo original através do circuito simples formado por uma fonte de tensão $V_{th}$ em série com um resistor $R_{th}$: 

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=\large$R_{th}$] (0,3) 
      to[V=\large$V_{th}$, invert] (3,3) 
      to[short, i<=$i$] (6,3) 
      to[open, *-*, v=$v$] (6,0) 
      to[short] (3,0) 
      to[short] (0,0);

\draw (3,0) to[open] (3,3);

\node[above=2pt] at (6,3) {$e_1$};
\node[below=2pt] at (6,0) {$e_2$};

\end{circuitikz}
\end{document}
```

E graças ao [[UFPE/2026.1/Circuitos 1/Teoremas de Rede/Teorema da superposição]], sabemos que independente do circuito conectado externamente entre os terminais a contribuição do componentes internos não mudará e portanto, fizemos uma simplificação do nosso circuito.

Sintetizando então, o processo consiste em duas etapas:

1. Obter $V_{th}$ calculando ou medindo a tensão do circuito aberto na rede original, isto é, com os valores originais de tensão e corrente.
2. Obter $R_{th}$ calculando ou medindo a resistência da rede de circuito aberto no terminal designado, com todas as fontes de tensão e corrente internas zeradas.

O grande poder desse teorema é a simplificação de partes inteiras do circuito podendo então ignorar grande parte de seus detalhes e olhar exclusivamente para uma parte do circuito que estamos interessados.