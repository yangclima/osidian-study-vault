Uma classe muito interessante de [[Transformações Conformes]] é a de **Transformações Lineares Fracionárias** também chamadas de [[Transformações lineares|transformações]] de Möbius ou bilineares, das quais fazem parte as [[Transformações Lineares complexas]], isto é, as [[Transformações complexas|transformações]] lineares são uma caso específico de transformação fracionária linear. 

Em geral, essas transformações são da forma:

$$
T(z) = \dfrac{az+b}{cz + d}
$$

Onde $a$, $b$, $c$ e $d$ são [[Números Complexos|constantes complexas]], essa transformação pode ser decomposta, por facilidade, em 3 transformações que já conhecemos:

1. $T_1(z) =cz + d$
2. $T_2(z) = \dfrac{1}{z}$
3. $T_3(z) = Az + B$

Onde $A = \dfrac{bc - ad}{c}$ e $B = \dfrac{a}{c}$. 

Se $ad - bc \neq 0$ então essa transformação é conforme e biunívoca em todo o seu domínio e possui um [[Zeros e Polos|polo]] em $-d/c$, podendo, desde que $c\neq 0$, ser estendida numa transformação:

$$T(z) = 
\begin{cases}
\dfrac{az + b}{bz+d}; \text{ se } z \neq -\dfrac{d}{c} \text{ e } z\neq \infty \\ \\

\infty; \text{ se } z = -\dfrac{d}{c} \\ \\ 

\dfrac{a}{c}; \text{ se } z = \infty

\end{cases}$$

Um propriedade interessante dessas transformações é a chamada preservação das retas e circunferências, basicamente, qualquer reta ou circunferência que não passa pelo polo da transformação ($z = -d/c$) é mapeada em uma circunferência, de forma similar, qualquer reta ou circunferência que passa nesse polo é mapeada numa reta.