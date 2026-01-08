O conceito de [[Impedância]] generaliza a ideia de [[Resistência]] para circuitos [[Circuitos RLC]], ou seja, circuitos que possuem **resistores, [[Indutores]] e [[Capacitores]]** simultaneamente. Diferentemente dos resistores, indutores e capacitores não dissipam energia, mas a armazenam temporariamente nos campos elétrico e magnético, o que introduz um **adiantamento ou atraso de fase** entre a tensão e a corrente.

Devido a essa defasagem, as contribuições desses elementos não podem ser somadas de forma puramente escalar. A representação dos parâmetros do circuito por meio de [[Números Complexos]] permite então incorporar naturalmente tanto a magnitude quanto a fase das grandezas envolvidas, simplificando a análise e possibilitando que as contribuições dos diferentes elementos sejam somadas de forma algébrica.

Considere o circuito a seguir:

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

Seja a tensão da [[Fontes de Corrente Alternada|fonte AC]] dada por $V(t) = V_0\cos{(\omega t)}$, usando a [[Fórmula de Euler]], definimos então a **tensão complexificada** como:

$$
V_C(t) = V_0e^{i\omega t} \implies V(t) = Re(V_C(t))
$$

E como nesse circuito  a corrente é definida como $I(t) = I_0\cos{(\omega t - \phi)}$ podemos fazer o mesmo para definir a **corrente complexificada** como:

$$
I_C(t) = I_0e^{i(\omega t - \phi)} \implies I(t) = Re(I_C(t))
$$

Assim, definimos a impedância como um número $Z = x + yi = |Z|e^{i\delta}$ tal que:

$$
V_C(t) = ZI_C(t) \implies V_0e^{i\omega t} = |Z|e^{i\delta}I_0e^{i(\omega t - \phi)}
$$

Que podemos simplificar para:

$$
V_0 = |Z|I_0e^{i(\delta - \phi)}
$$

Mas, como $V_0$ é um número real, então $\delta = \phi$ e então:

$$
V_0 = |Z|I_0
$$

A impedância pode então ser escrita como:

$$
Z = R + iX
$$

Onde $R$  é a resistência e $X$ é a reatância do circuito, da mesma forma, definimos a **admitância** como:

$$
Y = \dfrac{1}{Z} = \dfrac{1}{R + iX} = \dfrac{R - iX}{R^2 + X^2} = G + Bi
$$

Onde $G = 1/R$ é a **Condutância** e $B = 1/X$ é a **Susceptância**.

Analisando os elementos dos circuitos, encontramos que:

$$
X = X_L + X_C = \omega L - \dfrac{1}{\omega C}
$$

Então, a impedância é:

$$
Z = R+ \left(\omega L - \dfrac{1}{\omega C}\right)i
$$

Nesse caso:

$$
\phi = \arctan{\left(\dfrac{\omega L - \dfrac{1}{\omega C}}{R}\right)}
$$

E também:

$$
|Z| = \sqrt{(R)^2 + \left(\omega L-\dfrac{1}{\omega C}\right)^2}
$$

