A adição [[Introdução a 1s e 0s digitais|binária]] é feita de maneira semelhante a adição de decimais, a ideia é somar termo a termo, partindo do bit menos significante para o mais significante, nesse caso, só podem surgir quatro possibilidades:

- $0 + 0 = 0$
- $1 + 0 = 1$
- $1 + 1 = 0 + \text{carry de 1 para próxima posição}$
- $1 + 1 + \text{carry de 1 da posição anterior} = 1 + \text{carry de 1 para próxima posição}$

O *carry* é o famoso "vai um", quando completamos o valor máximo para uma posição, precisamos passar o valor excedente para a próxima, nesse caso como em binário $1 + 1 = 10$, quando surge essa operação deixamos $0$ na posição atual e passamos uma carry de 1 para a próxima.

Além da adição, podemos, de maneira parecida, realizar a subtração, partindo, mais uma vez, do bit menos significante para o mais significante, nesse caso, mais uma vez surgirão 4 possibilidades:

- $0 - 0 = 0$
- $1-1=0$
- $1-0=1$
- $0 - 1= \text{10 emprestado} - 1 = 1$

Veja que quando temos $0 -1$ precisamos "tomar emprestado" das posições posteriores.

Algumas vezes, ao realizar uma adição ou subtração, o resultado da operação tem um valor com magnitude superior ao que pode ser armazenado pelo número de bits dos valores participantes da operação, isso pode ocorrer na soma de dois números de mesmo sinal ou na subtração de dois números de sinal oposto, damos o nome de *Overflow aritmético* a esse fenômeno.
