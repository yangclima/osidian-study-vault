Até agora, ao considerar os circuitos [[Circuitos RC sem fontes|RC]] e [[Circuitos RL sem fontes|RL]], estivemos  lidando apenas com versões desses circuitos que não possuem a presença de fontes, isto é, circuitos nos quais a resposta se devia completamente a energia armazenada em [[Capacitores em circuitos|capacitores]] ou [[Indutores em Circuitos|indutores]]. Passaremos agora a ver circuitos onde além da energia armazenada nesses elementos, temos uma fonte constante excitando o circuito.

Os problemas que encontraremos aqui serão sempre relacionados a inserção de uma fonte ou de um capacitor/indutor no circuito em um instante $t$ com a ativação de um *switch*.

Ao resolver esses problemas, nos depararemos então com [[Equações Diferenciais]] de primeira ordem não homogêneas de modo que a resposta do circuito sempre consistirá em uma solução homogênea, a resposta natural do circuito, somada a um solução particular, a resposta desse circuito a excitação externa. No caso de uma fonte constante, a resposta natural do circuito irá tender a $0$ ao avançar do tempo, por isso, também a chamamos de resposta transitória, enquanto chamamos a resposta que se preserva ao longo do tempo de resposta permanente, ou resposta em regime permanente.

Como um exemplo, temos o seguinte circuito:

```tikz
\usepackage{circuitikz}

\begin{document}

\begin{circuitikz}[american]

\draw[scale=1]
(0,0) to[isource, i=$I_0$] 
(0,3) -- 
(3,3) to[R=$R$] 
(3,0) --
(0,0);

\draw[scale=1]
(3,3) to[switch, t=$t=0$]
(6,3) to[C=$C$]
(6,0) --
(3,0);

\end{circuitikz}

\end{document}
```

Nele, considerando $t>0$ e aplicando [[Lei de Kirchhoff das Correntes|LKC]] no nó superior iremos obter a EDO:

$$i_R + i_C = I_0 \implies \dfrac{V}{R} + C\dfrac{dV}{dt} = I_0$$


No [[Cálculo 4]] aprendemos diversas formas de resolver essa equação, por exemplo, o [[Método dos Fatores Integrantes]] que se aplicado nos dará:

$$V(t) = I_0R + Ae^{-t/RC}$$

Onde $A$ é uma constante e depende das condições iniciais do circuito, assim, como sabemos que para o capacitor $V(0^+) = V(0^-)$ teremos que, se antes da ativação do *switch* a [[Potencial elétrico|tensão]] no capacitor era $V_0$, então $V(0) = V_0$ e portanto encontraremos:

$$A = V_0 - I_0R$$

E nossa solução portanto, resposta do circuito é:

$$V(t) = I_0R + (V_0 - I_0R)e^{-t/RC}$$

De modo que $I_0R$ é a resposta em regime permanente do circuito e $(V_0 - I_0R)e^{-t/RC}$ é a resposta transitória.

No caso específico de uma fonte constante de excitação, obteremos sempre, seja pra indutor ou capacitor, uma EDO do tipo:

$$\dfrac{y}{dt} + Py = Q$$

Onde $P$ e $Q$ são constantes e portanto a solução será sempre:

$$y(t) = Ae^{-Pt} + \dfrac{P}{Q}$$
