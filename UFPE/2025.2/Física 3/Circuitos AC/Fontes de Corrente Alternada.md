Vimos que, pela [[Lei de Faraday]] da indução, um [[Fluxo magnético]] que varia no tempo induz uma [[Força eletromotriz]]. Em particular, se uma espira gira com uma velocidade angular $\omega$ na presença de um [[Campo Magnético]] $\vec B$ a força eletromotriz induzida irá variar senoidalmente o que resulta num [[Corrente]] alternada, também chamada de **corrente AC** (*Alternating Current*) e provê uma fonte de energia alternada.

Usamos o seguinte símbolo para representar uma fonte de corrente alternada:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\ctikzset{switches/scale=2}
\draw 
(0,0)to[sV]
(6,0);
\end{circuitikz}
\end{document}
```

Um exemplo de fonte de corrente alternada é:

$$
V(t) = V_0\sin(\omega t)
$$

Onde $V_0$ é o valor máximo que a [[Potencial elétrico|tensão]] da fonte assume, denominado **amplitude**, além disso, o argumento da função seno é $\phi_V = \omega t$ é denominado **fase da fonte de energia**. Como a função seno é periódica, isso significa que a tensão em um dado instante $t$ será exatamente a mesma num instante posterior $t^\prime = t + T$ onde $T$ é o **período**, nesse caso, definimos então a a **frequência** da fonte como $f = 1/T$ e então, a sua frequência angular é definida como $\omega = 2\pi f = 2\pi / T$.


