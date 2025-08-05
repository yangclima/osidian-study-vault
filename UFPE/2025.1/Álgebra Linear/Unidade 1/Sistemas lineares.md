# Equação linear
**Equação linear** no $\mathbb{R}^n$ é uma equação do tipo $a_1X_1 + a_2X_2 + \cdots a_nX_n= b$ onde $X$ são as variáveis e os coeficientes $a_1, a_2, \cdots, a_n$ e $b$ são números conhecidos.

# Sistema linear
A partir dessa definição, um **sistema linear** $m \times n$ é um conjunto de $m$ equações lineares definidas em $n$ variáveis.

# Solução
Uma **solução** para um sistema linear é um vetor $\mathbf{x} = |x_1, x_2, \cdots, x_n |^T$ tal que as substituições $X_1 = x_1, X_2 = x_2,\cdots, X_n = x_n$ satisfazem todas as equações lineares do sistema.

# Conjunto solução
O conjunto solução de um sistema linear é o conjunto de todos os vetores de $n$ variáveis que são soluções desse sistema linear. Normalmente esse conjunto é denotado por $Sol(S)$.

# Representação matricial
Um sistema linear pode ser representado através de [[Matrizes]] utilizando uma [[Multiplicação de matrizes]] do tipo $AX = B$ onde $A$ é a matriz dos coeficientes, $X$ é a matriz das incógnitas e $B$ é a matriz dos membros do sistema linear, sendo assim, temos:
$$
\begin{vmatrix}
a_11 \ \cdots \ a_1n \\
\cdots \\
a_{m1} \ \cdots \ a_{mn}
\end{vmatrix}
\times
\begin{vmatrix}
X_1\\
\ \cdots \ \\
\ X_n \
\end{vmatrix}
=
\begin{vmatrix}
b_1\\
\ \cdots \ \\
\ b_m \
\end{vmatrix}
$$
A representação também pode ser feita através de uma matriz ampliada:
$$
\begin{vmatrix}
\ A \ | \ \mathbf{b} \ 
\end{vmatrix}
=
\begin{vmatrix}
a_11 \ \cdots \ a_1n \ \ \ b_1\\
\cdots \\
a_{m1} \ \cdots \ a_{mn} \ \ \ b_m
\end{vmatrix}
$$

# Sistemas lineares homogêneos
Os sistemas lineares homogêneos são sistemas lineares onde todos os membros são nulos, ou seja, onde $b$ é um vetor-coluna nulo na representação matricial (Em resumo: $AX = 0$). Nesse caso específico, o conjunto solução desse sistema $Sol(S)$ é denominado **espaço de anulamento da matriz $A$** e é denotado por $\mathcal{N}(A)$, além disso, conjuntos solução de sistemas lineares homogêneos são considerados [[Subespaços Vetoriais]] do $\mathbb{R}^n$. 

## Sistemas lineares não homogêneos
Um **sistema linear não homogêneo** $(S) \ \ AX = b$ é um sistema linear onde o vetor-coluna $b$ não é nulo, nesse caso, supondo que $S$ tem pelo menos uma solução $x_0$, onde $Ax_0 = b$, então dado um vetor $x \in \mathbb{R}^n$ será uma solução de $S$ se e somente se $A(x - x_0) = b$, ou seja, se $x$ for uma solução para o **sistema linear homogêneo associado** a $S$, assim todos os vetores pertencentes a $Sol(S)$ podem ser obtidos somando um vetor pertencente a solução sistema linear homogêneo associado $(S^\prime) \ \ AX = 0$ ao vetor $x_0$.
$$
Sol(S) = \{ x_0 + z: z \in Sol(S^\prime) \}
$$
Caso o sistema linear não homogêneo $AX = b$ tenha solução, seu conjunto solução $Sol(S)$ é um Subespaço Afim paralelo ao subespaço linear homogêneo associado, sendo também portanto, o próprio  subespaço linear homogêneo associado translado pelo vetor $x_0$.
# Resolução de sistemas lineares
Uma das maneiras mais simples de se realizar a resolução de um sistema linear é realizando o [[Escalonamento de matrizes|escalonamento]] desse sistema linear, mais especificamente da matriz composta $[\ A \ \ | \ \ \mathbf{b} \ ]$ obtendo uma matriz linha- equivalente a ela, a matriz $[\ A^\prime \ \ | \ \ \mathbf{b}^\prime \ ]$, o fato é que, ao trabalhar com um sistema linear $AX = b$, se ele estiver escalonado, é muito fácil de identificar as variáveis livres desse sistema, além disso, o escalonamento e mais especificamente o [[Escalonamento de matrizes#Posto e Nulidade de uma matriz|posto]] $p$ da matriz $A_{m \times n}$ podem nos dar algumas informações imediatas sobre o conjunto solução do sistema:
- Se $p = n$ então o sistema tem solução única
- Se $p < n$ então o sistema tem infinitas soluções
- Se $p > n$ então o sistema não tem solução
- O sistema linear tem $p - n$ variáveis livres, esse valor também é chamado de grau de liberdade do sistema ou de [[Escalonamento de matrizes#Posto e Nulidade de uma matriz|nulidade]] da matriz $A$.