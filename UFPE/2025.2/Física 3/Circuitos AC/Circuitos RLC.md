---
tags:
  - anky
---
Agora que conhecemos o comportamento oscilatório dos [[Circuitos LC]], queremos verificar o que acontece adicionando um [[Resistência|resistor]] ao circuito o que fará com que a energia do sistema seja agora dispersada o que culmina num comportamento oscilatório amortecido.

Considere o seguinte circuito:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\ctikzset{switches/scale=2}
\draw 
(0,6)to[L=$L$]
(0,0)to[normal open switch=$S$]
(6,0)to[C=$C$]
(6,6)to[R=$R$](0,6);
\end{circuitikz}
\end{document}
```

Aqui, o [[Capacitores|capacitor]] está inicialmente com uma carga $Q_0$ e em $t=0$ a chave $S$ é fechada permitindo que a [[Corrente]] flua pelo circuito, diferente de um circuito LC onde $\dfrac{dU}{dt} =0$, nesse circuito, a energia é dissipada pelo resistor a uma taxa de $I^2R$ e portanto, a energia do sistema decai a uma taxa de $\dfrac{dU}{dt} = -I^2R$ e temos então:

$$
U = U_E + U_B = \dfrac{Q^2}{2C} + \dfrac{LI^2}{2}
$$
$$
\dfrac{dU}{dt} = LI\dfrac{dI}{dt} + \dfrac{Q}{C}\dfrac{dQ}{dt} = -I^2R
$$

Dividindo por $I = \dfrac{dQ}{dt}$, obtemos:

$$
\dfrac{dU}{dt} = L\dfrac{dI}{dt} + \dfrac{Q}{C} = -IR
$$

E portanto:

$$
L\dfrac{d^2Q}{dt^2} + \dfrac{Q}{C} + R\dfrac{dQ}{dt} = 0
$$

Essa é uma equação diferencial de segunda ordem e a sua solução é:

$$
Q(t) = Q_0e^{-\gamma t}\cos{(\omega^\prime t + \phi)}
$$

Onde $\gamma = \dfrac{R}{2L}$ e $\omega^\prime$, a nova frequência angular do sistema é  $\omega^\prime = \sqrt{\omega_0^2 - \gamma^2}$.

O caso em que estamos interessados é o caso em que $\omega_0 > \gamma$ e portanto $\omega^\prime$ é real e positivo, esse caso é chamado de **amortecimento subcrítico** e nele o sistema apresenta um comportamento oscilatório com amplitude exponencial dada por $Q_0e^{-\gamma t}$ tendo como gráfico característico o seguinte:

```tikz
\usepackage{amsmath,amssymb}
\usetikzlibrary{decorations.pathreplacing}
\begin{document}
\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[domain=0:15]
  \draw[very thin,color=gray] (0,-8) grid (16,8);

  \draw[->] (0,-8) -- (0,8) node[right] {$q(t)$};
  \draw[->] (-0.2,0) -- (16,0) node[right] {$t$};
  
  \draw[color=orange] plot (\x,{5*exp(-0.2*\x)*cos(0.97*\x r)});
  \draw[color=red,dashed] plot (\x,{5*exp(-0.2*\x)});
  \draw[color=red,dashed] plot (\x,{-5*exp(-0.2*\x)});
 
\end{tikzpicture}
\end{document}
```

A curva destacada em laranja é justamente a carga no capacitor, enquanto a destacada em vermelho é a amplitude exponencial $\pm Q_0e^{-\gamma t}$.

Como a carga é definida como a carga no capacitor e a corrente aqui é definida como a corrente que sai do capacitor, temos que:

$$
I(t) = -\dfrac{dQ}{dt} = Q_0e^{-\gamma t}\omega^\prime\left(\dfrac{\gamma}{\omega^\prime}\cos{(\omega^\prime t)} + \sin{(\omega^\prime t)}\right) 
$$

Porém para um $R$ pequeno, a seguinte relação é uma ótima aproximação:

$$
I(t) = \dfrac{Q_0}{\sqrt{LC}}e^{-\gamma t}\sin{(\omega^\prime t + \delta)}
$$

Onde $\delta = \arctan{\left(\dfrac{\gamma}{\omega^\prime}\right)}$.