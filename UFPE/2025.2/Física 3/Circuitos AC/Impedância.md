Como vimos ao analisar o funcionamento dos [[Circuitos RLC forçados]], cada elemento ([[Resistência|Resistores]], [[Capacitores]] e [[Indutores]]) apresenta uma "resistência" característica a passagem da corrente, no caso dos elementos indutivos e capacitivos, a **reatância capacitiva** $X_C$ e a **reatância indutiva** $X_L$ fazem então papel de uma resistência efetiva no circuitos puramente capacitivos e puramente indutivos, por outro lado, nos [[Circuitos RLC]] em série essa resistência efetiva é a soma vetorial das resistências oferecidas por cada um dos elementos, chamada de **impedância** e dada por:

$$
Z = \sqrt{(X_R)^2 + (X_L-X_C)^2} = \sqrt{(R)^2 + \left(\omega L-\dfrac{1}{\omega C}\right)^2}
$$

Assim, podemos definir a [[Corrente]] como sendo:

$$
I(t) = \dfrac{V_0}{Z}\sin{(\omega t)}
$$

E portanto, o módulo da corrente é dado por:

$$
I_0 = \dfrac{V_0}{Z}
$$

Para pensar de maneira intuitiva em impedância podemos utilizar a seguinte relação geométrica entre impedância e as reatâncias de onde podemos extrair valores como a magnitude da impedância, o cosseno e o seno da constante de fase:

```tikz
\begin{document}
\begin{tikzpicture}[scale=2]
% ---- Eixos ----
\draw[thick,-] (0,0) -- (4,0);
\draw[thick,-] (0,0) -- (4,3);
\draw[thick,-] (4,3) -- (4,0);

\node at (1.8,1.8) {$Z$};
\node at (4.6,1.5) {$X_L - X_C$};
\node at (2,-0.2) {$X_R$};

\draw[thick] (0.9,0) arc[start angle=0,end angle=36.09,radius=0.9];
\node at ({0.78*cos(36.09/2) + 0.4},{0.78*sin(36.09/2) + 0.2}) {$\phi$};

\end{tikzpicture}

\end{document}
```
