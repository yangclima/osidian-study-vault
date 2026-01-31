---
tags:
  - anky
---
Como já vimos, quando temos um [[Campo Magnético]] variando no tempo em um [[Circuitos DC|Circuito]] fechado a integral do [[Campo Elétrico]] ao longo desse circuito deixa de ser nula, pela [[Lei de Faraday]], temos:

$$
\oint \vec E \cdot d\vec s = - \iint \dfrac{\partial}{\partial t} \vec B \cdot d \vec A
$$

Isso ocorre para qualquer circuito onde a [[Corrente]] varia no tempo devido justamente aos campos elétricos induzidos associados ao fenômeno da [[Autoindutância]].

O nosso objetivo é agora então resolver circuitos simples levando em consideração esses efeitos. Considerando o seguinte circuito


```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\ctikzset{switches/scale=2}
\draw 
(0,6)to[battery1, a=$\varepsilon$]
(0,0)to[normal open switch=$S$]
(6,0)to[L=$L$]
(6,6)to[R=$R$](0,6);
\end{circuitikz}
\end{document}
```


Podemos encontrar que nesse circuito, quando $S$ é fechado é válida a relação:

$$
\varepsilon - RI - L\dfrac{dI}{dt} = 0
$$

Por mais que muitos livros didáticos ensinem que a obtenção desse resultado advém das [[Leis de Kirchhoff]], mais especificamente da Lei de Kirchhoff das tensões e que a queda de tensão ao longo do [[Indutores|indutor]] é $- L\dfrac{dI}{dt}$, e aliás, pensar dessa maneira até leve a um resultado correto, isso é fisicamente confuso já que num circuito sem indutância essa lei é apenas uma declaração de que o [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico]] ao longo de uma malha é $0$, o que em geral não é verdade quando temos correntes que variam no tempo. 

Apesar disso, pela questão mnemônica continuamos a chamar isso de Lei de Kirchhoff das Tensões, agora numa versão expandida, e enunciamos:

> Se um indutor é atravessado na direção da corrente a queda de tensão ao longo do mesmo é dada por $- L\dfrac{dI}{dt}$, atravessando o indutor no sentido contrário a corrente temos então uma queda de tensão dada por $L\dfrac{dI}{dt}$.

Voltando ao nosso circuito, considerando que não há energia magnética armazenada no indutor e que aa chave $S$ é fechada no instante $t=0$, devido a presença da [[Força eletromotriz]] induzida a corrente $I(t)$ do circuito não atinge imediatamente o seu máximo ($\varepsilon/R$) e $I(0) = 0$, nesse caso, podemos encontrar como solução para a nossa equação diferencial:

$$
\varepsilon - RI - L\dfrac{dI}{dt} = 0
$$
Pelo método da [[Separação de variáveis]] obtemos então:

$$
\int_0^t \dfrac{dt}{L} = \int_0^I \dfrac{dI^\prime}{\varepsilon - I^\prime R}
$$

E portanto:

$$
I(t) = \dfrac{\varepsilon}{R}(1 - e^{-\left(\dfrac{R\cdot t}{L}\right)})
$$

Expressão que pode ser simplificada como

$$
I(t) = I_{max}(1 - e^{-t/\tau})
$$

E portanto segue o seguinte gráfico característico:

```tikz
\usepackage{amsmath,amssymb}
\usetikzlibrary{decorations.pathreplacing}
\begin{document}
\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[domain=0:15]
  \draw[very thin,color=gray] (0,0) grid (16,8);

  \draw[<->] (0,-0.2) -- (0,3.160602)  node[left] {$I_{max}(1-e^{-1})$} -- (0,5) node[left] {$I_{max}$} -- (0,8) node[right] {$q(t)$};
  \draw[<->] (-0.2,0) -- (5,0) node[below] {$\tau = L/R$} -- (16,0) node[right] {$t$};
  
  \draw[color=orange] plot (\x, {5*(1 - exp(-\x/5))});
  \draw[color=red,dashed] plot (\x,{5});
  \draw[color=red,dashed] (5,0) -- (5,3.160602);
  \draw[color=red,dashed] (0,3.160602) -- (5,3.160602);
\end{tikzpicture}
\end{document}
```

Onde $I_{max} = \varepsilon / R$ e $\tau$ é a chamada constante de tempo do circuito e dada então pela relação $\tau = L / R$, nesse caso a força eletromotriz induzida pelo indutor é:

$$
|\varepsilon_L| = R\cdot I(t) =\varepsilon\cdot  e^{-t/\tau}
$$

E portanto, passado um tempo suficientemente longo, o indutor atua então como um condutor e não oferece mais resistência a corrente.

Nesse caso, a conservação de energia no sistema pode ser descrita por:

$$
I\cdot\varepsilon = I^2R + LI\dfrac{dI}{dt}
$$

Onde $\varepsilon\cdot I$ é a energia fornecida pela fonte, $I^2R$ é a energia dissipada pelo [[Resistência|resistor]] e $LI\dfrac{dI}{dt}$ é a taxa na qual a energia é armazenada no indutor (Essa equação pode ser obtida multiplicando por $I$ de ambos os lados a equação diferencial obtida por LKT no circuito).

Um outro caso importante de se analisar é o caso em que depois de um longo tempo decorrido (Energia máxima no indutor) a fonte é removida, nesse caso temos os seguinte circuito:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\ctikzset{switches/scale=2}
\draw 
(0,6)to[R=$R$]
(0,0)--
(6,0)to[L=$L$]
(6,6)--(0,6);
\end{circuitikz}
\end{document}
```

Nesse caso, o indutor passa a atuar como uma fonte de tensão de [[Força eletromotriz]] $\varepsilon_L$ e temos portanto:

$$
|\varepsilon_L| - RI = -L\dfrac{dI}{dt} - RI = 0
$$

E portanto:

$$
-\dfrac{dt}{L/R} = \dfrac{dI}{dt}
$$

Cuja solução é:

$$
I(t) = \dfrac{\varepsilon}{R}e^{-t/\tau}
$$

