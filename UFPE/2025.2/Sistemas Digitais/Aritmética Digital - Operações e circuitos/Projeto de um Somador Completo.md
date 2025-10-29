Como vimos, o Somador Completo é um [[Projetando Circuitos Lógicos Combinacionais|circuito lógico combinacional]] que serve como unidade básica de um [[Somador binário paralelo]] e consiste basicamente num circuito digital que recebe 3 bits como entrada ($A$, $B$ e $C_{in}$) e tem como saída dois bits ($S$ e $C_{out}$), utilizando o [[Mapa de Karnaugh]] ou a [[Simplificação Algébrica]], podemos chegar nas seguintes expressões:

$$
S = A \oplus B \oplus C_{in}
$$

$$
C_{out} = AB + BC_{in} + AC_{in}
$$

Ou seja:

![[sd_016.png]]

Existe também o **meio somador**, *half adder (HA)*, sua única diferença com relação ao FA é que ele opera apenas dois bits de entrada, $A$ e $B$, sem o $C_{in}$, nesse caso $S = A \oplus B$ e $C_{out} = AB$.