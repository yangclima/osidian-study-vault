Em geral, costumamos usar sistemas de numeração posicional para representar quantidades, sistemas onde a posição de cada dígito indica a potência que o dígito representa com relação a sua base $\beta$, isto é:

> Dado um número natural $\beta > 1$ e o conjunto de símbolos $\{\pm 0, 1, 2, 3, \cdots, \beta -1\}$ , a expressão: 
> $$(d_nd_{n-1}\cdots d_2d_1d_0,d_{-1}d_{-2})_\beta$$ 
> Representa o número no sistema de numeração decimal equivalente a
> $$d_n\beta^n+d_{n-1}\beta^{n-1}+\cdots +d_2\beta^2+d_1\beta + d_0\beta^0+d_{-1}\beta^{-1}+d_{-2}\beta^{-2}+\cdots$$

Exemplos de sistemas de numeração que seguem essa regra são os [[Sistemas de numeração digital|Sistema de numeração binário]], [[Sistema de numeração hexadecimal]], entre outros.

Infere-se da definição dada, o procedimento para decodificar um número escrito numa base $\beta$ qualquer em um número decimal, por outro lado, para codificar um número decimal $X$ em um sistema de numeração de base $\beta$ seguimos:

1. Primeiro separamos a parte inteira ($X^i$) e a parte fracionária ($X^f$) de $X$, tais que $X = X^i + X^f$,  $X^i = d_n\beta^n +d_{n-1}\beta^{n-1}+\cdots+d_1\beta +d_0$ e $X^f=d_{-1}\beta^{-1}+d_{-2}\beta^-2\cdots$ 
2. Considerando inicialmente somente a parte inteira, a dividimos por $\beta$, e obteremos assim $\frac{X^i}{\beta} = d_n\beta^{n-1} +d_{n-1}\beta^{n-2}+\cdots+d_1 +\frac{d_0}{\beta}$, de modo que  $d_0$ é o resto da divisão de $X^i$ por $\beta$ , do mesmo modo, $d_1$ é o resto de $d_n\beta^{n-1} +d_{n-1}\beta^{n-2}+\cdots+d_1$  na divisão por $\beta$ e assim sucessivamente
3. Agora, considerando a parte fracionária $X^f = d_{-1}\beta^{-1}+d_{-2}\beta^{-2}+\cdots$  de modo que, multiplicando por $\beta$, teremos $X^f = d_{-1}+d_{-2}\beta^{-1}+\cdots$  de modo que, a parte inteira do resultado dessa multiplicação é $d_{-1}$, multiplicando a parte fracionária desse resultado por $\beta$ obteremos $d_{-2}$ e assim sucessivamente

É importante notar que a precisão é especificada pelo número de casas após a vírgula no número convertido, de modo que se especificado que se quer um número com 4 casas decimais, por exemplo, o algoritmo para assim que o $d_{-4}$ for calculado.

Esse método, entretanto, só funciona para transformar números no sistema decimal para um sistema de base $\beta$ e *vice-versa*, para conversões entre sistemas com bases $\beta_1$ e $\beta_2$ geralmente se converte da primeira base para decimal e então de decimal para a segunda base usando o procedimento já descrito.

Pode-se, entretanto, aproveitar-se da relação entre algumas bases específicas para facilitar o processo de conversão, por exemplo, considerando o sistema de base $2$ e o sistema de base $16$, como $2^4 = 16$, 4 dígitos de um número escrito no sistema binário equivalem exatamente a um dígito escrito no sistema hexadecimal, o que permite a conversão entre esses sistemas agrupando, a partir da vírgula, os algarismos em grupos de 4.