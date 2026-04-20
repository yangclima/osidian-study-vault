Duas configurações muito comuns de se ver na engenharia elétrica, quanto ao formato da disposição dos elementos são a configurações Delta (Ou Pi) e a configuração Y (Ou Estrela) e em algumas situações de resolução de problema, é conveniente poder converter entre essas duas configurações.

A configuração $\Delta$, também chamada de Triângulo ou $\pi$, vista para os [[Resistores Lineares]] tem o seguinte formato:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american, scale=2.0]

\node[circ, label=below:C] (C) at (0,0) {};
\node[circ, label=right:B] (B) at (1.5,3) {};
\node[circ, label=left:A] (A) at (-1.5,3) {};

\draw
(C) to[R=$R_a$] 
(B) to[R=$R_c$] (A)
to[R=$R_b$] (C);

\end{circuitikz}
\end{document}
```

Ou, de maneira equivalente:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american, scale=2.0]

\node[circ, label=below:C] (C) at (0,0) {};
\node[circ, label=right:B] (B) at (1.5,3) {};
\node[circ, label=left:A] (A) at (-1.5,3) {};

\draw
(1.5,0) to[R=$R_a$] 
(B) to[R=$R_c$] (A)
to[R=$R_b$] (-1.5,0);

\draw
(-2,0) -- (2,0);

\end{circuitikz}
\end{document}
```

Já a configuração $Y$, também chamada de $T$ ou Estrela tem o seguinte formato:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american, scale=2.0]

\node[circ, label=below:C] (C) at (0,0) {};
\node[circ, label=right:B] (B) at (1.5,3) {};
\node[circ, label=left:A] (A) at (-1.5,3) {};

\draw
(C) to[R=$R_3$] (0, 1.5);

\draw
(A) to[R=$R_1$] (0, 1.5);

\draw
(B) to[R=$R_2$] (0, 1.5);

\end{circuitikz}
\end{document}
```

Ou, de forma equivalente:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american, scale=2.0]

\node[circ, label=below:C] (C) at (0,0) {};
\node[circ, label=right:B] (B) at (1.5,3) {};
\node[circ, label=left:A] (A) at (-1.5,3) {};

\draw
(C) to[R=$R_3$] (0, 3);

\draw
(A) to[R=$R_1$] (0, 3);

\draw
(B) to[R=$R_2$] (0, 3);

\end{circuitikz}
\end{document}
```

Para converter então entre essas duas configurações, usamos:
# Delta $\to$ Estrela
$$R_1 = \dfrac{R_bR_c}{R_a + R_b + Rc}$$
$$R_2 = \dfrac{R_aR_c}{R_a + R_b + Rc}$$
$$R_3 = \dfrac{R_aR_b}{R_a + R_b + Rc}$$

# Estrela $\to$ Delta
$$R_a = \dfrac{R_1R_2 + R_1R_3 + R_2R_3}{R_1}$$
$$R_a = \dfrac{R_1R_2 + R_1R_3 + R_2R_3}{R_2}$$
$$R_a = \dfrac{R_1R_2 + R_1R_3 + R_2R_3}{R_3}$$


