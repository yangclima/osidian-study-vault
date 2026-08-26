Até agora só vimos fontes independentes enquanto [[Componentes Ideais]], como elementos que independente da situação fornecem a mesma [[Potencial elétrico|tensão]] ou a mesma [[Corrente|corrente]], na vida real, no entanto, nos deparamos com fontes cujo fornecimento de tensão ou corrente dependem da carga conectada a ela, carga essa que pode ser interpretada como uma resistência $R_L$, nesse caso, um modelo muito mais fiel ao comportamento real da fonte está relacionado com os equivalentes de [[Teorema de Thévenin|Thévenin]] e [[Teorema de Norton|Norton]], isto é, nos terminais da fonte temos uma tensão:

$$v = v_g - R_gi$$

Onde $v_g$ e $R_g$ são parâmetros da fonte real, também chamada de fonte prática, de modo que quando conectamos uma carga $R_L$ ao sistema temos:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,3) to[V=$v_g$] (0,0);
\draw
(0,3) to[R=$R_g$] (3,3);
\draw
(0,0) -- (3,0);
\draw
(3,0) to[R=$R_L$] (3,3);

\node[circ, label=above:a] (C) at (3,3) {};
\node[circ, label=below:b] (C) at (3,0) {};

\end{circuitikz}
\end{document}
```

Nesse circuito:
$$i = \dfrac{v}{R_L} = \dfrac{v_g -R_gi}{R_{L}} \implies i = \dfrac{v_g}{R_{L}+ R_g}$$

$$v = \dfrac{R_Lv_g}{R_L +R_g }$$

de modo que, como vemos, a tensão nos terminais da fonte bem como a corrente entre eles, depende dos parâmetros da fonte, mas também da carga conectada, de tal modo que a tensão da fonte só atinge o nível perfeito, para $R_L = \infty$ e só atinge o nível perfeito de corrente para $R_L = 0$.

O mesmo modelo é satisfeito quando substituímos a fonte de tensão $v_g$ em série com um [[Resistores Lineares|resistor]] $R_g$ por uma fonte de corrente $i_g$ em paralelo com uma resistência $R_g$. 

Isso ainda abre margem para o chamado **Teorema da máxima transferência de energia** que consiste em maximizar a potência entregue a carga $R_L$, pode-se provar, através da resolução de um problema de [[Otimização]], que essa máxima transferência ocorre quando $R_g = R_L$