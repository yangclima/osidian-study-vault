Em muitos circuitos digitais, aparece a combinação de circuitos [[Operação AND|AND]] e [[Operação OR|OR]] dada pela seguinte [[Descrevendo Circuitos Lógicos Algebricamente|expressão booleana]]:

$$
x = \bar A \bar B + A B 
$$

Que tem a seguinte tabela-verdade:

| $A$ | $B$ | $x$ |
| --- | --- | --- |
| $0$ | $0$ | $1$ |
| $0$ | $1$ | $0$ |
| $1$ | $0$ | $0$ |
| $1$ | $1$ | $1$ |

Perceba que essa porta retorna $1$ sempre que os níveis de suas entradas são iguais e $0$ sempre que estes são diferentes (O inverso da [[Operação XOR]]). Por sua ampla aplicação essa porta recebe um nome específico, porta XNOR ou Exclusive-NOR (NÃO-OU Exclusivo) é denotada algebricamente da seguinte forma:

$$
x = \overline{A \oplus B}
$$

Além disso, seu símbolo é o seguinte:

![[sd_011.png]]
