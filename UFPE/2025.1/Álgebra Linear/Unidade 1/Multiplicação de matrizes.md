A multiplicação de [[Matrizes]] é uma operação realizada entre duas matrizes do tipo:
$$
\begin{vmatrix}
a_{11} , \cdots , a_{1n} \\
\cdots , \cdots , \cdots \\
a_{m1} , \cdots , a_{mn}
\end{vmatrix}_{m \times n}
\times
\begin{vmatrix}
b_{11} , \cdots , b_{1p} \\
\cdots , \cdots , \cdots \\
b_{n1} , \cdots , b_{np}
\end{vmatrix}_{n \times p}
=
\begin{vmatrix}
c_{11} , \cdots , c_{1p} \\
\cdots , \cdots , \cdots \\
c_{m1} , \cdots , c_{mp}
\end{vmatrix}_{m \times p}
$$
Note que a quantidade de colunas da primeira matriz deve ser igual ao número de linha da segunda e que a multiplicação retorna uma matriz com o mesmo número de linhas da primeira matriz e mesmo número de colunas da segunda matriz.
# Caso trivial (Produto escalar)
O caso trivial da multiplicação de matriz é multiplicar um vetor linha por um vetor coluna o que retornará uma matriz $1 \times 1$, ou seja, um escalar e é o mesmo que realizar um produto escalar entre dois vetores:
$$
\begin{vmatrix}
x_1 \ x_2 \ \cdots \ x_n
\end{vmatrix}
\times
\begin{vmatrix}
y_1 \\ y_2 \\ \cdots \\ y_n
\end{vmatrix}
=
x_1y_1 + x_2y_2 + \cdots + x_ny_n
$$
# Produtos da forma $Ax$
Um produto da forma $Ax$ é o produto entre uma matriz $A_{m \times n}$ e uma matriz  $x_{n \times 1}$ resultando numa matriz $C_{m \times 1}$ que pode ser descrita como combinação linear das colunas de $A$ utilizando os elementos de $x$ como coeficientes.
$$
\begin{vmatrix}
a_{11} , \cdots , a_{1n} \\
\cdots , \cdots , \cdots \\
a_{m1} , \cdots , a_{mn}
\end{vmatrix}
\times
\begin{vmatrix}
x_1 \\ \cdots \\ x_n
\end{vmatrix}
=
x_1 \cdot 
\begin{vmatrix}
a_{11} \\ \cdots \\ a_{m1}
\end{vmatrix} +
x_2 \cdot 
\begin{vmatrix}
a_{12} \\ \cdots \\ a_{m2}
\end{vmatrix} + \cdots +
a_n \cdot 
\begin{vmatrix}
a_{1n} \\ \cdots \\ a_{mn}
\end{vmatrix}
$$
# Produtos da forma $x^{T}A$
Um produto da forma $x^{T}A$ é o produto entre uma matriz $x^{T}_{1 \times m}$  e uma matriz  $A_{m \times n}$ resultando numa matriz $C_{m \times 1}$ que pode ser descrita como combinação linear das linhas de $A$ utilizando os elementos de $x$ como coeficientes.
$$
\begin{vmatrix}
x_1 \ \cdots \ x_n
\end{vmatrix}
\times
\begin{vmatrix}
a_{11} , \cdots , a_{1n} \\
\cdots , \cdots , \cdots \\
a_{m1} , \cdots , a_{mn}
\end{vmatrix}
=
x_1 \cdot 
\begin{vmatrix}
a_{11} \ \cdots \ a_{1n}
\end{vmatrix} + \cdots +
x_2 \cdot
\begin{vmatrix}
a_{m1} \ \cdots \ a_{mn}
\end{vmatrix}
$$
# Produtos da forma $A_{m \times n} B_{n \times p}$
## Descrição por linhas
O produto de matrizes do tipo $A_{m \times n} B_{n \times p}$ pode ser descrito através de suas linhas, onde a $i$-ésima linha da matriz $C_{m \times p} = A_{m \times n} B_{n \times p}$ pode ser dada pelo produto da $i$-ésima linha de $A$ com a matriz $B$, temos portanto
$$
C_{m \times p} = A_{m \times n} B_{n \times p} = 
\begin{vmatrix}
\mathbf{a}_1^TB \\
\mathbf{a}_2^TB \\
\cdots \\
\mathbf{a}_m^TB
\end{vmatrix}
$$
## Descrição por colunas
O produto de matrizes do tipo $A_{m \times n} B_{n \times p}$ pode ser descrito também através de suas colunas, onde a $j$-ésima coluna da matriz $C_{m \times p} = A_{m \times n} B_{n \times p}$ pode ser dada pelo produto da matriz $A$ com $j$-ésima coluna de $B$, temos portanto:
$$
C_{m \times p} = A_{m \times n} B_{n \times p} = 
\begin{vmatrix}
A\mathbf{b}_1 \ | \ A\mathbf{b}_2 \ | \ \cdots \ | \ A\mathbf{b}_p
\end{vmatrix}
$$
## Descrição por elementos
Além das descrições por linhas e por colunas, o produto $A_{m \times n} B_{n \times p}$ pode ser descrito também elemento por elemento onde o elemento $c_{ij}$ da matriz $C_{m \times p} = A_{m \times n} B_{n \times p}$ pode ser dada pelo produto da $i$-ésima linha de $A$ com a  $j$-ésima coluna de $B$, temos portanto:
$$
C_{m \times p} = A_{m \times n} B_{n \times p} = 
\begin{vmatrix}
\mathbf{a}_1^T\mathbf{b}_1 \ \mathbf{a}_1^T\mathbf{b}_2 \ \cdots \ \mathbf{a}_1^T\mathbf{b}_j \\
\cdots \\
\mathbf{a}_j^T\mathbf{b}_1 \ \mathbf{a}_j^T\mathbf{b}_2 \cdots \mathbf{a}_i^T\mathbf{b}_j
\end{vmatrix}
$$
# Propriedades da multiplicação de matrizes
1. Distributividade: $A(B + C) = AB + AC$ 
2. Associatividade: $A(BC) = (AB)C$
3. Elemento Neutro: $I_mA = AI_n = A$
4. Transposta: $(AB)^T = B^TA^T$
