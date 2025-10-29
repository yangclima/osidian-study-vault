Em muitos circuitos digitais, aparece a combinação de circuitos [[Operação AND|AND]] e [[Operação OR|OR]] dada pela seguinte [[Descrevendo Circuitos Lógicos Algebricamente|expressão booleana]]:

$$
x = A \bar B + \bar A B 
$$

Que tem a seguinte tabela-verdade:

| $A$ | $B$ | $x$ |
| --- | --- | --- |
| $0$   | $0$   | $0$ |
| $0$   | $1$   | $1$ |
| $1$   | $0$   | $1$ |
| $1$   | $1$   | $0$ |

Perceba que essa porta retorna $0$ sempre que os níveis de suas entradas são iguais e $1$ sempre que estes são diferentes. Por sua ampla aplicação essa porta recebe um nome específico, porta XOR ou Exclusive-OR (OU Exclusivo) é denotada algebricamente da seguinte forma:

$$
x = A \oplus B
$$

Além disso, seu símbolo é o seguinte:

![[sd_010.png|center]]
