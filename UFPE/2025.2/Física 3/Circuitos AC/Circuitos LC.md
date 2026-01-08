Os circuitos que vimos até agora eram chamados de [[Circuitos DC]] ou circuitos de corrente contínua já que a [[Corrente]] tinha um direção constante (Apesar de que nos [[Circuitos RC]] e nos [[Circuitos RL]] a corrente de carregamento tinha direção oposta a corrente de descarga), agora veremos o primeiro circuito onde a corrente muda de direção com um frequência bem definida, denominados de **Circuitos AC** ou circuitos de corrente alternada.

Considere o seguinte circuito, como a chave $S$ inicialmente aberta, no qual um [[Capacitores|capacitor]] de capacitância $C$ inicialmente carregado com uma carga $Q_0$ está conectado a um [[Indutores|indutor]] inicialmente descarregado de indutância $L$.

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\ctikzset{switches/scale=2}
\draw 
(0,6)to[L=$L$]
(0,0)to[normal open switch=$S$]
(6,0)to[C=$C$]
(6,6)--(0,6);
\end{circuitikz}
\end{document}
```

Fechando a chave $S$ no instante $t=0$ o capacitor começa a descarregar e a energia $U_E$ armazenada nele então decresce enquanto o indutor começa a resistir pelo fenômeno da [[Autoindutância]] a mudança na corrente e portanto a energia nele armazenada $U_B$ aumenta até alcançar o seu máximo quando $U_E = 0$ (Capacitor completamente descarregado), nesse momento o indutor começa a descarregar carregando novamente o capacitor com uma corrente na direção oposta a inicial, na ausência de [[Resistência]] elétrica, esse ciclo continua infinitamente e temos:

$$
U = U_B + U_E = \dfrac{LI^2}{2} + \dfrac{Q^2}{2C} = cte
$$

Como não a energia dissipada, é também verdade que:

$$
\dfrac{dU}{dt} = LI\dfrac{dI}{dt} + \dfrac{Q}{C}\dfrac{dQ}{dt} = 0
$$

Porém, como $I = dQ/dt$ temos:

$$
\dfrac{dU}{dt} = LI\dfrac{d^2Q}{dt^2} + \dfrac{Q}{C}\dfrac{dQ}{dt} = 0
$$

Equação diferencial, cuja solução geral é:

$$
Q(t) = Q_0\cos(\omega t + \phi)
$$

Onde $Q_0$ é a **amplitude de carga**, a carga máxima do capacitor, $\phi$ é uma constante de fase que depende das condições iniciais do circuito em $t=0$ e $\omega$ é a **frequência angular** de oscilação do sistema dada por:

$$
\omega = \dfrac{1}{\sqrt{LC}}
$$

E a corrente é então:

$$
I(t) = \dfrac{dQ}{dt} = -Q_0\omega\sin(\omega t + \phi)
$$

Onde $I_0$, a corrente máxima é dada por $I_0 = \omega Q_0$.

Temos então o seguinte gráfico característico onde a carga aparece em laranja e a corrente em verde:

```tikz
\usepackage{amsmath,amssymb}
\usetikzlibrary{decorations.pathreplacing}
\begin{document}
\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[domain=0:15]
  \draw[very thin,color=gray] (0,-4) grid (16,4);

  % Eixo Y
  \draw[<->] (0,-4) -- (0,1.5) node[left] {$I_0$} -- (0,3) node[left] {$Q_0$} -- (0,4) node[right] {$q(t)$};
  % Eixo X
  \draw[<->] (-0.2,0) -- (4*3.14,0) node [below] {T} -- (16,0) node[right] {$t$};
  
  \draw[color=orange] plot (\x, {3*cos(0.5*\x r)});
  \draw[color=green] plot (\x, {1.5*sin(0.5*\x r)});
  \draw[color=red, dashed] plot (\x, 3);
  \draw[color=red, dashed] (4*3.14,0) -- (4*3.14,3);
  \draw[color=red, dashed] plot (\x, 1.5);
\end{tikzpicture}
\end{document}
```

O $T$ marcado no gráfico é o **período de oscilação** do circuito, o tempo que o circuito leva para sair de um estado e retornar ao mesmo estado, este, é dado por:

$$
T = \dfrac{2 \pi}{w} = 2\pi\sqrt{LC}
$$