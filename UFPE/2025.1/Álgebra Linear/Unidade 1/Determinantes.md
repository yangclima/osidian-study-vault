O Determinante é um número real associado a uma [[Matrizes|matriz]] quadrada que nos dá informações importantes sobre essa matriz e sobre o [[Sistemas lineares|sistema linear]] que ela representa, o determinante pode ser calculado da seguinte forma:
- Para uma matriz $A = [a_{ij}]_{1\times1}$, $\det{(A)} = a$
- Para uma matriz $A = [a_{ij}]_{2\times2}$, $\det{(A)} = a_{11}\cdot a_{22} - a_{12}\cdot a_{21}$
- Para uma matriz quadrada de ordem superior a $2$ podemos utilizar o Teorema de Laplace para definir $\det{(A)}$ através da $i$-ésima linha onde $det(A) = \sum_{j=1}^{j = n} (-1)^{i + j} \cdot a_{ij} \cdot det(A_{ij})$  ou da $j$-ésima coluna de $A$, onde o determinante é $det(A) = \sum_{i=1}^{i = n} (-1)^{i + j} \cdot a_{ij} \cdot det(A_{ij})$ 
# Mudanças devido as operações elementares
As operações elementares podem ser muito úteis para calcular mais facilmente o determinante, porém podem ocasionar certas mudanças no determinante de uma matriz:
$$
L_a \rightarrow \lambda L_a \implies \det{(A)} \rightarrow \lambda\det{(A)}
$$
$$
L_a \rightarrow L_a + \lambda L_b \implies \det{(A)} \rightarrow \det{(A)}
$$
$$
L_a \leftrightarrow L_b \implies \det{(A)} \rightarrow -\det{(A)}
$$
# Propriedades
As principais propriedades do determinantes são:
1. $\det{(A^T)} = \det{(A)}$
2. $\det{(A^{-1})} = \dfrac{1}{\det{(A)}}$
3. $\det{(AB)} = \det{(A)} \cdot \det{(B)}$
4. $\det{(I)} = 1$
5. Se $A$ é uma matriz triangular $\det{(A)} = a_{11}a_{22}\ \dots \ a_{nn}$, ou seja o produto das entradas da diagonal principal
