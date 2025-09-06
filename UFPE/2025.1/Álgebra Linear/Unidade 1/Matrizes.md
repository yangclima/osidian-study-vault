A compreensão da álgebra linear começa pelo conceito de [[MIT - Courses/Classical Mechanic/Vetores]],que aqui, deixam de ter apenas significado geométrico, ou seja, passam a ser vistos como representando diversos tipos de informações. 
# Matrizes como representações de vetores
Como afirmamos acima, os vetores, na álgebra linear tem muito mais que apenas o significado geométrico, assim, não precisamos mais os limitar a 3 dimensões, podendo utilizar vetores n-dimensionais, também chamados de n-úplas:
$$
\bf{a}= \begin{vmatrix}  
a_1 \\
a_2 \\
\ \dots \ \\
a_n
\end{vmatrix}
$$
Ou seja, representando vetores como matrizes-coluna de n componentes (A representação é válida tanto para representar vetores como pontos, não haverá distinção entre esses dois).  Utilizando mais de um vetor, podemos criar arranjos retangulares denotados por 
$$
A = \begin{vmatrix}  
a_{ij}
\end{vmatrix}
_{m \times n}
$$
# Tipos de matrizes
Os principais tipos de matrizes são: Matriz linha, coluna, quadrada, diagonal e identidade. 
- Uma **matriz linha** é uma matriz do tipo $1 \times n$
- Uma **matriz coluna** é uma matriz do tipo $m \times 1$
- Uma **matriz quadrada** é uma matriz do tipo $m \times m$
- Uma **matriz diagonal** é uma matriz quadrada que só possui valores não nulos na sua diagonal principal
- Uma **matriz identidade** é uma matriz diagonal na qual todos os elementos da diagonal principal tem valor 1
- Uma **matriz nula** é uma matriz que possui todos os elementos iguais a zero
# Operações entre matrizes
## Soma de matrizes
$$
\begin{vmatrix}  
a & b \\
c & d \\
\end{vmatrix}
+
\begin{vmatrix}  
e & f \\
g & h \\
\end{vmatrix}
= 
\begin{vmatrix}  
a + e & b +f \\
c + g & f + h \\
\end{vmatrix}
$$
Propriedades
- Comutativa $A + B = B + A$
- Associativa $A + (B + C) = (A + B) + C$
- Elemento neutro $A + 0 = A$
- Elemento inverso $A + (-A)= 0$
## Multiplicação por escalar
$$
\lambda\begin{vmatrix}  
a & b \\
c & d \\
\end{vmatrix}
= 
\begin{vmatrix}  
\lambda a & \lambda b \\
\lambda c & \lambda d \\
\end{vmatrix}
$$
Propriedades
- Associativa $\alpha(\lambda A) = (\alpha A)\lambda$
- Distributiva sobre a adição $\lambda (A + B) = \lambda A + \lambda B$
- Elemento neutro $1 \cdot A = A$ 
## Transposta
Uma matriz transposta $A^T$ é uma transformação da matriz $A$ tal que 
$$
\begin{vmatrix}  
(a_{ij}
\end{vmatrix}^T 
= 
\begin{vmatrix}  
(a_{ji}
\end{vmatrix}
$$
Propriedades:
- Comutativa $\lambda (A^T) = (\lambda A)^T$
- Distributiva sobre a soma $(A + B)^T = A^T + B^T$
