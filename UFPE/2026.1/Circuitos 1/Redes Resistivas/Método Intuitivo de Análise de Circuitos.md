---
prev: "[[Divisores de Tensão e Corrente]]"
---
Utilizando agora nossas noções na utilização da [[Lei de Kirchhoff das Correntes]] e da [[Lei de Kirchhoff das Tensões]] e tendo em mente como os resistores funcionam em circuitos como os [[Divisores de Tensão e Corrente]], podemos desenvolver um método menos sistemático embora também muito mais simples para analisar nossos circuitos.

A ideia é simplificar o circuito substituindo conjuntos de [[Resistores Lineares]] por um único resistor linear com [[Resistência]] equivalente ao conjunto, para tal, precisamos ter em mente que, para $N$ resistores em série a resistência equivalente $R_{eq}$ é dada por:

$$
R_{eq} = R_1 + R_2 + \cdots + R_N
$$

Já para $N$ resistores em paralelo, denotados por $R_1 || R_2 || \cdots || R_N$, vale que:

$$
\dfrac{1}{R_{eq}} = \dfrac{1}{R_1} + \dfrac{1}{R_2} + \cdots + \dfrac{1}{R_N}
$$

Assim, utilizando o fato de que a [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]] é a mesma para resistores em paralelo e que a [[Corrente]] é a mesma para resistores em série e que, por fim, determinando a corrente em um resistor, conseguimos definir a tensão nesse mesmo resistor e *vice-versa*, então, podemos utilizar facilmente esse método para encontrar as nossas variáveis de circuito.

Tomando por exemplo o seguinte circuito:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_1$] (3,0)
to[R=$R_2$] (3,3) -- (0,3);

\draw
(3,0) -- 
(6,0) to[R=$R_3$] 
(6,3) -- (3,3);

\end{circuitikz}
\end{document}
```

Então, podemos simplificá-lo para:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_1$] (3,0)
to[R=$R_{eq}$] (3,3) -- (0,3);


\end{circuitikz}
\end{document}
```

onde $R_{eq} = \dfrac{R_2R_3}{R_2 + R_3}$ e então, simplificá-lo novamente para:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) -- (3,0)
to[R=$R_{eq}$, v=$v$, i=$i$] (3,3) -- (0,3);


\end{circuitikz}
\end{document}
```

onde $R_{eq} = R_1 + \dfrac{R_2R_3}{R_2 + R_3}$, assim, podemos achar a corrente nesse resistor como sendo:

$$
i\cdot R_{eq} = -V \implies i = \dfrac{-V(R_2 + R_3)}{R_1R_2 + R_1R_3 + R_2R_3}
$$

Que, pela topologia do circuito, deve ser a corrente no $R_1$, então:

$$
i_1 = \dfrac{-V(R_2 + R_3)}{R_1R_2 + R_1R_3 + R_2R_3}
$$

Além disso, a queda de tensão no resistor $R_1$ deve ser de:

$$
v_1 = \dfrac{-VR_1(R_2 + R_3)}{R_1R_2 + R_1R_3 + R_2R_3}
$$

Assim, a queda de tensão em cada resistor do conjunto em paralelo deve ser:

$$
-V-v_1 -v_2 =  0 \implies i_2R_2 =  -V + \dfrac{VR_1(R_2 + R_3)}{R_1R_2 + R_1R_3 + R_2R_3}
$$

E portanto:

$$
i_2 =  \dfrac{-VR_3}{R_1R_2 + R_1R_3 + R_2R_3}
$$

E, da mesma maneira:

$$
i_3 =  \dfrac{-VR_2}{R_1R_2 + R_1R_3 + R_2R_3}
$$

Assim, obtemos o mesmo resultado que no [[Método Básico de Análise de Circuitos]], mas sem utilizar os sistemas lineares.