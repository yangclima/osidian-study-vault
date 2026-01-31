---
tags:
  - anky
---
Os equipamentos elétricos passivos sobre os quais atua o fenômeno da [[Autoindutância]] ou autoindutância são denominados **indutores**, estes por sua vez, devido ao fenômeno citado apresentam uma resistência à passagem da corrente sendo portanto necessária a atuação de uma fonte externa de [[Força eletromotriz]] para que se estabeleça uma corrente através desses equipamentos, assim, pelo teorema do trabalho-energia, concluímos que **energia pode ser armazenada num indutor**, assim, estes indutores podem efetuar nos sistemas um papel semelhante ao dos [[Capacitores]].

A [[Potência]] ou taxa na qual a força eletromotriz externa $\varepsilon_{ext}$ realiza trabalho para superar a força eletromotriz auto induzida $\varepsilon_L$ e passar a corrente $I$ no indutor é:

$$
P_L = \dfrac{dW_{ext}}{dt} = I\cdot\varepsilon_{ext}
$$

Se apenas o indutor e a fonte externa estiverem presentes,  então $\varepsilon_{ext}= \varepsilon_L$
o que implica que:

$$
P_L = \dfrac{dW_{ext}}{dt} = -I\varepsilon_L =IL\dfrac{dI}{dt}
$$

E portanto:

$$
W_{ext} = \int_0^I LI^\prime dI^\prime = \dfrac{1}{2}L\cdot I^2
$$

Nesse caso, definimos a **energia magnética** como:

$$
U_B = \dfrac{1}{2}L\cdot I^2
$$
# Densidade de energia magnética
Assim como definimos a densidade de energia elétrica $u_E$, imaginando que a energia seja de fato armazenada no volume do campo magnético, podemos deduzir a **densidade de energia magnética** $u_B$:

$$
u_B = \dfrac{U_B}{Vol} = \dfrac{B^2}{2\cdot\mu_0}
$$

De tal forma que:

$$
U_B = \iiint\limits_{indutor} u_B \,dV
$$

O que é válido mesmo para um [[Campo Magnético]] não uniforme. 

Por fim, uma outra maneira de definir a indutância é então:

$$
L = \dfrac{2U_B}{I^2}
$$

Nos dando uma nova intuição física sobre a indutância de um indutor: Uma medida da quantidade de energia que podemos armazenar nele para uma [[Corrente]] $I$.


Ao representar esse tipo de aparato em um [[Circuitos DC|circuito]] utilizamos o seguinte símbolo:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\draw 
(0,0)to[L=$L$](4,0);
\end{circuitikz}
\end{document}
```