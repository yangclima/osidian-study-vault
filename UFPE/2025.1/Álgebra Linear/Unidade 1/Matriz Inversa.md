A matriz inversa de uma [[Matrizes|matriz]] $A_{n\times n}$, denotada por $A^{-1}$ é uma matriz $B_{n \times n}$ que satisfaz:
$$
B \text{ é a inversa de } A \iff
\begin{cases}
BA = I_n \\
AB = I_n 
\end{cases}
$$
Ou seja, o produto de $B$ por $A$ e o produto de $A$ por $B$ resultam na matriz identidade de ordem $n$, saiba que é desperdício de tempo testar o produtos $AB$ e $BA$ já que neste caso em específico
$$
B_{n \times n}A_{n \times n} = I_n \implies A_{n \times n}B_{n \times n} = I_n 
$$
Existem algumas propriedades interessantes relacionadas a matriz inversa e a inversibilidade de uma matriz:
- Ela possui unicidade: se uma matriz $A$ possui inversa essa inversa é única.
- Uma matriz $A$ possui inversa se, e somente se o [[Determinantes|determinante]] dessa matriz é não nulo, ou seja $\det{(A)} \neq 0$
- Devido a definição acima a respeito do determinante de uma matriz, para que um matriz $A$ seja inversível ela precisa ter seu [[Escalonamento de matrizes#Posto e Nulidade de uma matriz|posto]] $p$ igual a sua ordem $n$, ou seja, $p = n$
# Eliminação Gauss-Jordan
A eliminação Gauss-Jordan é a maneira mais simples de se encontrar a matriz inversa $A^{-1}$ de uma dada matriz $A$, isso pode ser feito concatenando $A$ à matriz identidade de mesma ordem, criando uma nova matriz expandida $(A|I_n)$ e aplicando a ela operações elementares de modo a transformar $A$ na matriz identidade, o que ocasionará na transformação de $I$ na matriz $A^{-1}$, ou seja:
$$
\left( A \,|\, I_n \right) \xrightarrow{\text{Operações Elementares}} \left( I_n \,|\, A^{-1} \right)
$$
