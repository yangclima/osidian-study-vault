Quando uma [[Fontes de Corrente Alternada|Fonte de Corrente Alternada]] é conectada a um [[Circuitos RLC|Circuito RLC]], a energia fornecida pela fonte compensa a energia dissipada pelo [[Resistência|resistor]] e as oscilações não serão mais amortecidas, sendo então chamadas de **Oscilações forçadas** ou de **Oscilações Dirigidas**.

Depois de um tempo inicial transitório, uma [[Corrente]] alternada irá fluir no circuito como resposta a fonte de tensão forçada. Essa corrente temo mesmo caráter senoidal da [[Potencial elétrico|tensão]] e é dada por:

$$
I(t) = I_0\sin{(\omega t - \phi)}
$$

E oscila na mesma frequência angular $\omega$ que a fonte, tem amplitude $I_0$ e fase dada por $\phi_I = \omega t - \phi$ e a constante de fase $\phi$ depende da frequência angular da fonte. A **diferença de fase**, também chamada de **defasagem** entre a tensão e a corrente é dada por:

$$
\Delta \phi = \phi_V - \phi_I = \omega t - (\omega t - \phi) = \phi
$$

Antes de analisar o circuito RLC por completo, é interessante que consideremos os casos onde apenas um de cada um dos três elementos ([[Capacitores]], [[Indutores]] e [[Resistência|Resistores]]) está conectado na fonte de corrente AC.

# Carga puramente resistiva
Considere o seguinte circuito, onde a tensão da fonte é $V(t) = V_0\sin{(\omega t)}$:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick, scale=3]
\ctikzset{
  font=\Large,
}
\draw 
(0,2)to[sI]
(0,0)--
(2,0)to[R, l_=$\ R$]
(2,2)--(0,2);
\end{circuitikz}
\end{document}
```

Como se espera, a corrente no resistor é dada por:

$$
I_R(t) = I_0\sin(\omega t + \phi_R)
$$

Além disso, usando as [[Leis de Kirchhoff]] obtemos:

$$
V(t) - I_R(t)R = 0 \implies I_R(t) = \dfrac{V_0}{R}\sin(\omega t) = I_0\sin{(\omega t)}  = I_0\sin{(\omega t -\phi_R)} 
$$

Daí, obtemos que, no caso de uma **carga puramente resistiva** no circuito a defasagem entre tensão e corrente é $\Delta \phi_R = \phi = 0$ e vale também que:

$$
I_0 = \dfrac{V_0}{R} = \dfrac{V_0}{X_R}
$$

Onde a quantidade $X_R$ é denominada **reatância resistiva** do circuito, assim chamada para concordar com a nomenclatura que introduziremos para os elementos indutivos e capacitivos, mas que, nesse caso, não deixa de ser apenas a resistência com a qual já estamos acostumados.

O comportamento de $I_R(t)$ pode também ser descrito através do que chamamos de **diagrama fasorial**, um **fasor** é um vetor rotativo que possui magnitude, velocidade angular e projeção, por exemplo o fasor da tensão é denotado por $\vec V$ tem amplitude constante $V_0$ e projeção $V_0\sin{(\omega t)}$ que equivale a tensão da fonte num dado instante $t$, por outro lado, o fasor da corrente no resistor é $\vec I_R$, ele tem magnitude $I_0 = V_0/R$ e projeção $I_0\sin{(\omega t)}$ que equivale a corrente no resistor num dado instante $t$, graficamente, esses vetores são:

```tikz
\begin{document}
\begin{tikzpicture}[scale=2]
% ---- Eixos ----
\draw[thick,->] (-0.3,0) -- (4,0);
\draw[thick,->] (0,-0.3) -- (0,3.4);

% ---- Parâmetros (ajuste livre) ----
\def\ang{45}          % ângulo do vetor (graus)
\def\lenVR{3.2}       % comprimento de \vec V_{R0}
\def\lenIR{4.3}       % comprimento de \vec I_{R0}

% ---- Pontos finais dos vetores ----
\coordinate (O)  at (0,0);
\coordinate (VR) at ({\lenVR*cos(\ang)},{\lenVR*sin(\ang)});
\coordinate (IR) at ({\lenIR*cos(\ang)},{\lenIR*sin(\ang)});
\coordinate (projVR) at (0,{\lenVR*sin(\ang)});
\coordinate (projIR) at (0,{\lenIR*sin(\ang)});

% ---- Vetores (fasores) ----
\draw[ultra thick,purple!80!black,->] (O) -- (IR)
  node[above right=2pt] {$\vec I_{R}$};
\draw[densely dashed,gray] (projIR) node[left=2pt] {$I_R(t)$} -- (IR);

\draw[ultra thick,orange!85!black,->] (O) -- (VR)
  node[below right=2pt] {$\vec V$};
\draw[densely dashed,gray] (projVR) node[left=2pt] {$V(t)$} -- (VR);

\draw[thick] (0.9,0) arc[start angle=0,end angle=\ang,radius=0.9];
\node at ({0.78*cos(\ang/2) + 0.4},{0.78*sin(\ang/2) + 0.2}) {$\omega t$};

\end{tikzpicture}

\end{document}
```

# Carga puramente indutiva
Considere agora o circuito a seguir, onde a tensão da fonte é $V(t) = V_0\sin{(\omega t)}$:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick, scale=3]
\ctikzset{
  font=\Large,
}
\draw 
(0,2)to[sI]
(0,0)--
(2,0)to[L, l_=$\ \ L$]
(2,2)--(0,2);
\end{circuitikz}
\end{document}
```

Assim, como sabemos a corrente no indutor será:

$$
I_R(t) = I_0\sin{(\omega t - \phi_L)}
$$

Aplicando LKT obtemos:

$$
V(t) = L\dfrac{dI(t)}{dt} \implies I_L(t) = \int \dfrac{V(t)}{L}dt = \int \dfrac{V_0\sin{(\omega t)}}{L}dt
$$
Então:

$$
I_L(t) = -\dfrac{V_0}{\omega L}\cos{(\omega t)} = \dfrac{V_0}{\omega L}\sin{(\omega t - \dfrac{\pi}{2})} = I_0\sin{(\omega t - \phi_L)}
$$

Portanto, sabemos que $I_0 = 1/\omega L$ e $\phi_L = \pi/2$, isto é, a corrente no indutor está defasada (atrasada) com relação a tensão num fator de $\pi/2$, além disso:

$$
I_0 = \dfrac{V_0}{\omega L} = \dfrac{V_0}{X_L} \implies  X_L = \omega L
$$

Onde $X_L$ é denominada **indutância capacitiva** e tem, no Sistema Internacional, a unidade de $[\ohm]$  ("Ohms"), usando a representação fasorial, obtemos:

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
% ---- Eixos ----
\draw[thick,->] (-0.3,0) -- (4,0);
\draw[thick,<->] (0,-3.3) -- (0,3.4);

% ---- Parâmetros (ajuste livre) ----
\def\ang{45}          % ângulo do vetor (graus)
\def\angUm{45 - 90}          % ângulo do vetor (graus)
\def\lenVR{3.2}       % comprimento de \vec V_{R0}
\def\lenIR{4.3}       % comprimento de \vec I_{R0}

% ---- Pontos finais dos vetores ----
\coordinate (O)  at (0,0);
\coordinate (VR) at ({\lenVR*cos(\ang)},{\lenVR*sin(\ang)});
\coordinate (IR) at ({\lenIR*cos(\angUm)},{\lenIR*sin(\angUm)});
\coordinate (projVR) at (0,{\lenVR*sin(\ang)});
\coordinate (projIR) at (0,{\lenIR*sin(\angUm)});

% ---- Vetores (fasores) ----
\draw[ultra thick,purple!80!black,->] (O) -- (IR)
  node[above right=2pt] {$\vec I_{L}$};
\draw[densely dashed,gray] (projIR) node[left=2pt] {$I_L(t)$} -- (IR);

\draw[ultra thick,orange!85!black,->] (O) -- (VR)
  node[below right=2pt] {$\vec V$};
\draw[densely dashed,gray] (projVR) node[left=2pt] {$V(t)$} -- (VR);

\draw[thick] (0.9,0) arc[start angle=0,end angle=\ang,radius=0.9];
\node at ({0.78*cos(\ang/2) + 0.4},{0.78*sin(\ang/2) + 0.2}) {$\omega t$};

\end{tikzpicture}

\end{document}
```

# Carga puramente capacitiva
Por fim, considere o seguinte circuito, onde a tensão $V(t) = V_0\sin{(\omega t)}$:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick, scale=3]
\ctikzset{
  font=\Large,
}
\draw 
(0,2)to[sI]
(0,0)--
(2,0)to[C, l_=$\ C$]
(2,2)--(0,2);
\end{circuitikz}
\end{document}
```

Aqui, como você já deve esperar, esperamos que:

$$
I_R(t) = I_0\sin{(\omega t - \phi_C)}
$$

Então, por LKT obtemos:

$$
V(t) = \dfrac{q(t)}{C} \implies \dfrac{d}{dt}V(t) = \dfrac{d}{dt} \dfrac{q(t)}{C} \implies V_0\omega\cos{(\omega t)} = \dfrac{1}{C} I_C(t)
$$

Nesse caso:

$$
I_C(t) = CV_0\omega\sin{(\omega t + \dfrac{\pi}{2})} = I_0\sin{(\omega t - \phi_C)}
$$

Nesse caso, temos que $\phi_C = - \pi/2$ o que significa que a corrente está defasada da tensão por uma fator de $pi/2$, estando, nesse caso, adiantada com relação a tensão, além disso, assim como definimos para a carga indutiva:

$$
I_0 = \dfrac{V_0}{\dfrac{1}{\omega C}} = \dfrac{V_0}{X_C} \implies  X_L = \dfrac{1}{\omega C}
$$

Onde $X_C$ é denominada **reatância capacitiva** e assim como $X_R$ e $X_L$ tem como unidade no SI, a unidade de $[\ohm]$  ("Ohms"). Por fim, usando a representação fasorial, obtemos:

```tikz
\begin{document}
\begin{tikzpicture}[scale=1]
% ---- Eixos ----
\draw[thick,<->] (-4,0) -- (4,0);
\draw[thick,->] (0,-0.3) -- (0,3.4);

% ---- Parâmetros (ajuste livre) ----
\def\ang{45}          % ângulo do vetor (graus)
\def\angUm{45 + 90}          % ângulo do vetor (graus)
\def\lenVR{3.2}       % comprimento de \vec V_{R0}
\def\lenIR{4.3}       % comprimento de \vec I_{R0}

% ---- Pontos finais dos vetores ----
\coordinate (O)  at (0,0);
\coordinate (VR) at ({\lenVR*cos(\ang)},{\lenVR*sin(\ang)});
\coordinate (IR) at ({\lenIR*cos(\angUm)},{\lenIR*sin(\angUm)});
\coordinate (projVR) at (0,{\lenVR*sin(\ang)});
\coordinate (projIR) at (0,{\lenIR*sin(\angUm)});

% ---- Vetores (fasores) ----
\draw[ultra thick,purple!80!black,->] (O) -- (IR)
  node[above right=2pt] {$\vec I_{C}$};
\draw[densely dashed,gray] (projIR) node[right=2pt] {$I_C(t)$} -- (IR);

\draw[ultra thick,orange!85!black,->] (O) -- (VR)
  node[below right=2pt] {$\vec V$};
\draw[densely dashed,gray] (projVR) node[left=2pt] {$V(t)$} -- (VR);

\draw[thick] (0.9,0) arc[start angle=0,end angle=\ang,radius=0.9];
\node at ({0.78*cos(\ang/2) + 0.4},{0.78*sin(\ang/2) + 0.2}) {$\omega t$};

\end{tikzpicture}

\end{document}
```

# Circuito RLC forçado
Agora, unimos o que construímos conceitualmente analisando cada elemento do nosso circuito individualmente para chegar a uma conclusão geral para o circuito RLC forçado, a seguir:

```tikz
\usepackage{circuitikz} 
\begin{document}
\begin{circuitikz}[american voltages, thick, scale=3]
\ctikzset{
  font=\Large,
}
\draw 
(0,2)to[sI]
(0,0)to[R=$R$]
(2,0)to[C, l=$\ C$]
(2,2)to[L, l_=$L$](0,2);
\end{circuitikz}
\end{document}
```

Como a [[Potencial elétrico|tensão]] da fonte é $V(t) = V_0\sin{(\omega t + \phi)}$ e utilizando LKT, obtemos:

$$
V(t) = V_R(t) + V_L(t) + V_C(t) = RI + L\dfrac{dI}{dt} + \dfrac{q}{C} = V_0\sin{(\omega t + \phi)}
$$

Para deixar nossa equação diferencial em termos apenas da corrente, tomamos a [[Derivada]] temporal de ambos os lados, e dividimos a equação por $L$ obtendo:

$$
\dfrac{V_0\omega}{L}\cos{(\omega t + \phi)} = \dfrac{I}{LC} +\dfrac{R}{L}\dfrac{dI}{dt} + \dfrac{d^2I}{dt^2}
$$

Essa é a equação diferencial que rege o comportamento do nosso circuito, porém, mesmo sem resolvê-la, podemos encontrar a amplitude $I_0$ da corrente bem como a sua constante de fase $\phi$ examinando os fasores ligados a cada um dos três elementos do circuito:

```tikz
\begin{document}
\begin{tikzpicture}[scale=0.5]

% ================== DIAGRAMA CAPACITIVO ==================
\begin{scope}[xshift=-10cm]

\draw[thick, -] (-4,0) -- (4,0);
\draw[thick,-] (0,-4) -- (0,4);

% ---- Parâmetros (ajuste livre) ----
\def\ang{-90}          % ângulo do vetor (graus)
\def\angUm{-90 + 90}          % ângulo do vetor (graus)
\def\lenVR{3}       % comprimento de \vec V_{R0}
\def\lenIR{3.5}       % comprimento de \vec I_{R0}

% ---- Pontos finais dos vetores ----
\coordinate (O)  at (0,0);
\coordinate (VR) at ({\lenVR*cos(\ang)},{\lenVR*sin(\ang)});
\coordinate (IR) at ({\lenIR*cos(\angUm)},{\lenIR*sin(\angUm)});
\coordinate (projVR) at (0,{\lenVR*sin(\ang)});
\coordinate (projIR) at (0,{\lenIR*sin(\angUm)});

% ---- Vetores (fasores) ----
\draw[ultra thick,purple!80!black,->] (O) -- (IR)
  node[above right=2pt] {$\vec I_{C}$};

\draw[ultra thick,orange!85!black,->] (O) -- (VR)
  node[below right=2pt] {$\vec V_C$};

\node at (0,-5) {\large Capacitivo};

\end{scope}

\begin{scope}[xshift=0]

\draw[thick, -] (-4,0) -- (4,0);
\draw[thick,-] (0,-4) -- (0,4);

% ---- Parâmetros (ajuste livre) ----
\def\ang{0}          % ângulo do vetor (graus)
\def\angUm{0}          % ângulo do vetor (graus)
\def\lenVR{3}       % comprimento de \vec V_{R0}
\def\lenIR{3.5}       % comprimento de \vec I_{R0}

% ---- Pontos finais dos vetores ----
\coordinate (O)  at (0,0);
\coordinate (VR) at ({\lenVR*cos(\ang)},{\lenVR*sin(\ang)});
\coordinate (IR) at ({\lenIR*cos(\angUm)},{\lenIR*sin(\angUm)});
\coordinate (projVR) at (0,{\lenVR*sin(\ang)});
\coordinate (projIR) at (0,{\lenIR*sin(\angUm)});

% ---- Vetores (fasores) ----
\draw[ultra thick,purple!80!black,->] (O) -- (IR)
  node[above right=2pt] {$\vec I_{R}$};

\draw[ultra thick,orange!85!black,->] (O) -- (VR)
  node[below right=2pt] {$\vec V_R$};

\node at (0,-5) {\large Resistivo};

\end{scope}

\begin{scope}[xshift=10cm]

\draw[thick, -] (-4,0) -- (4,0);
\draw[thick,-] (0,-4) -- (0,4);

% ---- Parâmetros (ajuste livre) ----
\def\ang{90}          % ângulo do vetor (graus)
\def\angUm{0}          % ângulo do vetor (graus)
\def\lenVR{3}       % comprimento de \vec V_{R0}
\def\lenIR{3.5}       % comprimento de \vec I_{R0}

% ---- Pontos finais dos vetores ----
\coordinate (O)  at (0,0);
\coordinate (VR) at ({\lenVR*cos(\ang)},{\lenVR*sin(\ang)});
\coordinate (IR) at ({\lenIR*cos(\angUm)},{\lenIR*sin(\angUm)});
\coordinate (projVR) at (0,{\lenVR*sin(\ang)});
\coordinate (projIR) at (0,{\lenIR*sin(\angUm)});

% ---- Vetores (fasores) ----
\draw[ultra thick,purple!80!black,->] (O) -- (IR)
  node[above right=2pt] {$\vec I_{L}$};

\draw[ultra thick,orange!85!black,->] (O) -- (VR)
  node[below right=2pt] {$\vec V_L$};

\node at (0,-5) {\large Indutivo};
\end{scope}

\end{tikzpicture}
\end{document}
```

Usando a representação fatorial, obtemos então que:

$$
\vec V = \vec V_C + \vec V_R + \vec V_L \implies \vec V = | \vec V_C + \vec V_R + \vec V_L|
$$

Assim, a amplitude da tensão é dada por:

$$
V_0 = |\vec V| = \sqrt{(I_0X_R)^2 + (I_0X_L - I_0X_C)^2} = I_0\sqrt{(X_R)^2 + (X_L - X_C)^2}
$$

Substituindo as reatâncias na equação, obtemos:

$$
V_0 = I_0\sqrt{(R)^2 + (\omega L - \dfrac{1}{\omega C})^2}
$$

Usando então uma relação triangular observada na soma dos fasores, obtemos a constante de fase a partir de:

$$
\tan \phi = \dfrac{X_LI_0-X_CI_0}{X_RI_0} = \dfrac{X_L-X_C}{X_R} = \dfrac{1}{R}\left({\omega L -\dfrac{1}{\omega C}}\right)
$$

Nesse caso, temos:

$$
\phi = \arctan \left(\dfrac{1}{R}\left({\omega L -\dfrac{1}{\omega C}}\right)\right)
$$
