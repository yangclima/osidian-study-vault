O [[Sistemas de numeração digital|sistema de numeração binário]] tem a grande vantagem de possuir uma alta operabilidade em [[Introdução a 1s e 0s digitais|sistemas digitais]], já que utiliza apenas 1s e 0s para representar cada valor numérico, sua utilização, porém, é mais complicada por sua baixa inteligibilidade, ou seja, é mais complicado para nós humanos lidarmos com esse tipo de representação, para resolver esse problema, foi criado o **Sistema de numeração hexadecimal** que utiliza a base $16$ e utiliza como símbolos os números de $1$ a $9$ e as letras de $A$ a $F$ (Temos então a sequência: $0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F$), o $A$ equivale a $10$, o $B$ a $11$, o $C$ a $12$, o $D$ a $13$, o $E$ a $14$ e o $F$ a 15.

O sistema hexadecimal é mais fácil de reconhecer e oferece uma conversão mais simples para o sistema binário, já que as suas bases são múltiplos, assim, cada dígito hexadecimal é representado por $4$ dígitos binários, dessa maneira sua conversão é simples, veja:

> Para converter $10AF$ para binário convertemos cada dígito de uma vez (Utilizando sempre 4 dígitos binários, mesmo que estes sejam 0s): $1$ se torna $0001$, $0$ se torna $0000$, $A$ se torna $1010$, $F$ se torna $1111$, o hexadecimal $10AF$ equivale em binário a $0001000010101111$

Por outro lado, para converter de hexadecimal para decimal, multiplicamos cada valor pela sua potência de $16$ de acordo com a sua posição, assim, temos:

> Para converter $10AF$ para decimal fazemos $15\cdot16^0 + 10\cdot16^1 + 0\cdot16^2 + 1\cdot16^3 = 15 + 160 + 0 + 4096 = 4271$

