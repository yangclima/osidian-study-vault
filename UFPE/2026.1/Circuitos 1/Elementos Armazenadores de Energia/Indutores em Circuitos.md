Um [[Indutores|indutor]] é um dispositivo eletrônico de dois terminais composto por um fio condutor enrolado em espiral, no qual vale a relação:

$$\lambda = Li$$

Isto é, no qual o [[Fluxo magnético]] é proporcional a [[Corrente]] por uma constante de proporcionalidade $L$, mensurada em *Henries* $[H]$ denominada indutância, porém, através da [[Lei de Faraday]] podemos obter a relação $v-i$:

$$v = \dfrac{d\lambda}{dt} = L\dfrac{dI}{dt}$$

De modo que se a [[Corrente]] é constante, temos uma tensão nula, de modo que o indutor funciona como um curto circuito para a corrente contínua. Seguindo a [[Convenção de Variáveis Associadas]] representamos então:

```tikz
\usepackage{circuitikz}

\begin{document}

\begin{circuitikz}[american]

\draw[scale=1]
(0,0) to[short, i=i] (3,0) to[L=L] (3,-3) -- (0,-3) to[open, v<=v] (0,0);

\end{circuitikz}

\end{document}
```


De forma parecida ao comportamento dos [[Capacitores em circuitos]], variações instantâneas na [[Corrente]] em indutores requerem [[Potencial elétrico|tensões]] e portanto potência infinita, algo fisicamente impossível, por isso, dizemos que a corrente não varia instantaneamente nesses dispositivos e denotamos isso, considerando algo como o fechamento de um *switch* por:

$$i(0^-) = i(0^+)$$

Além disso, podemos calcular a corrente em um indutor a partir do histórico de tensões em seus terminais a partir da expressão:

$$i(t) = \dfrac{1}{L}\int_{t_0}^tv(t)dt + i(t_0) = \dfrac{1}{L}\int_{-\infty}^tv(t)dt$$

Quando a energia armazenada em indutores, temos a expressão:

$$w_L = \dfrac{1}{2}Li^2(t)$$

E quanto a sua associação, temos em série:

$$L_{eq} = \sum_i^n L_i$$

E em paralelo:

$$\dfrac{1}{L_{eq} } = \sum_i^n \dfrac{1}{L_i}$$