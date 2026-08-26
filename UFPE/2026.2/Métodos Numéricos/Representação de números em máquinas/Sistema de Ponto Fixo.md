O sistema de ponto fixo é um em que a parte inteira e a parte fracionária de um número são representadas com uma quantidade fixa de bits, isto é, utilizando $n$ bits podemos representar um número não inteiro usando:

- $(-1)^{d_{n-1}}(d_{n-2}\cdots d_{a},d_{a-1}\cdots d_1d_0)_2$ se representarmos o número usando um bit para o sinal, $a$ bits para a parte fracionária e $n-a$ bits para a parte inteira, aqui temos a representação dupla do zero
- $(d_{n-2}\cdots d_a)_2- d_{n-1}(2^{n-1-a} - 2^{-a}) + (0,d_{a-1}\cdots d_1d_0)_2$ se o sinal for representado usando o sistema de complemento de 1, continuamos  com a representação dupla do zero
- $(d_{n-2}\cdots d_a)_2- d_{n-1}(2^{n-1-a}) + (0,d_{a-1}\cdots d_1d_0)_2$ se o sinal for representado usando um [[Sistema de Complemento de 2|sistema de complemento de 2]].

Para **32** bits, geralmente usamos **16** bits para a parte fracionária e $15$ para a parte inteira