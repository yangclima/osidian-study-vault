Os computadores utilizam um número finito de bits para representar um número real, devido a isso, só conseguimos representar um subconjunto desses números de forma exata. Os valores desse subconjunto, que é finito e representado por $F$, são chamados de **Números de ponto flutuante**.

 A representação dos números reais no sistema de ponto flutuante é caracterizada por 4 parâmetros inteiros: a **base** $\beta$, a **precisão** $t$ e a **gama de expoentes** $[L,U]$.

Assim, pertencem ao subconjunto $F$, o número $0$ e todos os números da forma:

$$y = 0,d_1d_2\cdots d_t\times \beta^e; \ \ \ 0\leq d_i\leq \beta - 1;\ \ \ d_1\neq 0; \ \ \ L \leq e \leq U$$

Nesse caso, chamamos a sequência $d_1d_2\cdots d_t$ de **mantissa**. Assim, para qualquer $y\in F$ temos que a desigualdade $\beta^{L-1}\leq|y| \leq \beta^U(1-\beta^{-t})$ é verdadeira.

Os grandes problemas relacionados a esse sistema de representação numérica é que, primeiro, existe um limite para o tamanho dos números que podem ser representados (O que não é tão complicado nos computadores modernos já que os padrões atuais permitem representar números gigantescos, por exemplo, a Aritmética de precisão dupla do IEEE, amplamente adotada, permite representar números entre $1,7977\times 10^{308}$ e $2,2251\times 10^{308}$ reduzindo muito a chance de underflow ou overflow)  e, segundo, existem gaps entre os números que podem ser representados nesse sistema.

Basicamente, temos que nos recordar que o conjunto dos números de ponto flutuante é finito e o espaçamento entre números não é uniforme.