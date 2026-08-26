[[Capacitores]] são dispositivos de dois terminais constituídos por dois condutores separados por um material não condutor, às vezes chamado de isolador ou [[Dielétricos|dielétrico]]. Ao transferir cargas entre os dois condutores, o que, por conta do dielétrico precisa ser feito através de um circuito externo surge entre eles uma diferença de [[Potencial elétrico]], de modo que esses dispositivo obedece uma relação:

$$q = Cv$$

Ou seja, a [[carga]] no [[Resistores e Capacitores#Capacitores|capacitor]] é proporcional a diferença de potencial entre os seus terminais por uma constante de proporcionalidade $C$, chamada de **Capacitância** cuja unidade no S.I. é o *Farad* $[F]$.

Pela definição de [[Corrente]] podemos achar a relação $v-i$ do capacitor como:

$$i = \dfrac{dq}{dt} = C\dfrac{dv}{dt}$$


Assim, se $v$ é constante, temos $i=0$ de modo que o capacitor funciona como um circuito aberto em corrente contínua. Seguindo a [[Convenção de Variáveis Associadas]] representamos:

```tikz
\usepackage{circuitikz}

\begin{document}

\begin{circuitikz}[american]

\draw[scale=1]
(0,0) to[short, i=i] (3,0) to[C=C] (3,-3) -- (0,-3) to[open, v<=v] (0,0);

\end{circuitikz}

\end{document}
```

Dada a relação entre tensão e corrente no capacitor, uma mudança instantânea  da sua tensão exigiria que uma corrente infinita fluísse entre seus terminais o que levaria a uma potência infinita, fisicamente impossível de modo que mudanças instantâneas na tensão entre seus terminais são pode acontecer, por outro lado, a corrente pode ser descontínua, de forma similar, a carga total no capacitor não pode variar instantaneamente.

Podemos encontrar a tensão no tempo $v(t)$ em termos da corrente $i(t)$ que flui num capacitor através da relação:

$$v(t) = \dfrac{1}{C}\int_{t_0}^t i(t)dt + v(t_0) = \dfrac{1}{C}\int_{-\infty}^t i(t) dt$$

Quando a energia armazenada em um capacitor temos:

$$w_e(t) = \dfrac{1}{2}Cv^2(t) = \dfrac{Q(t)v(t)}{2}$$

Em muitos casos precisaremos estudar as grandezas em redes  ao realizar um chaveamento, a ativação de um switch no circuito, para isso, se um chaveamento ocorre em $t=0$  denotamos $t = 0^-$ é o instante imediatamente anterior ao chaveamento e $t = 0^+$ é o tempo imediatamente posterior a ele, de forma que, para o capacitor:

$$v_C(0^-) = v_C(0^+)$$

Quanto a associação de resistores, em série temos:

$$\dfrac{1}{C_{eq}} = \sum_i^n \dfrac{1}{C_i}$$

E em paralelo:

$$C_{eq} = \sum_i^n C_i$$

