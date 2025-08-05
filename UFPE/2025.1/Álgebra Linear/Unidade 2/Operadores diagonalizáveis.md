Dizemos que um [[Transformações lineares|Operador Linear]] $L$ é diagonalizável, se e somente se, existe uma [[Bases|base]] $\mathcal{B} = \{v_1, v_2, \cdots, v_n\}$ para a qual, $L$ pode ser descrito por uma [[Matriz de transformação linear]] diagonal, ou seja:
$$
[L]_{\mathcal{B}}^{\mathcal{B}} = 
\begin{bmatrix}
\lambda_1 & 0 & \cdots & 0 \\
0 & \lambda_2 & \cdots & 0 \\
\cdots & \cdots & \cdots & \cdots \\
\cdots & \cdots & \cdots & \cdots \\
0 & 0 & \cdots & \lambda_n
\end{bmatrix}
$$
Olhando apenas para a matriz do operador linear podemos definir que:
$$
A \text{ é diagonal} \iff A = PBP^{-1}
$$
Onde P é a [[Matriz de mudança de base]] da base $\mathcal{B}$ para a canônica, $P^{-1}$ é a sua inversa e B é $[L]_{\mathcal{B}}^{\mathcal{B}}$. Dizemos então que uma matriz é diagonalizável, se, e somente se, ela é semelhante a alguma matriz diagonal.

