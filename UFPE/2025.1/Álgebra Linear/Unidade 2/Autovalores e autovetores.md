Dado um vetor $v$ qualquer, **não nulo**, e uma [[Transformações lineares|transformação linear]] $L$, dizemos que $v$ é um **autovetor** de $L$ (Ou da matriz $A$, que é [[Matriz de transformação linear]] de $L$) quando ele satisfaz:
$$
L(v) = \lambda v
$$
Ou seja, quando $L$ manda $v$ em um múltiplo de $v$, $\lambda v$, chamamos então esse lambda de autovalor associado ao autovetor $v$. 

A grande utilidade desse conceito na álgebra linear é que, é que um operador linear $L$ é [[Operadores diagonalizáveis|diagonalizável]], se, e somente se, existe uma base $\mathcal{B}$ do $\mathbb{R}^n$ formada por autovetores de $L$ de forma que a matriz diagonal $B$, a qual a matriz de $L$ é semelhante, tem em sua diagonal, os autovalores $\lambda_1, \lambda_2, \cdots, \lambda_n$ associados respectivamente aos autovetores $v_1, v_2, \cdots, v_n$ que formam a base $\mathcal{B}$, já que $[L]v_1 = \lambda_1 v_1$ e as coordenadas de $\lambda_1 v_1$ com relação a $\mathcal{B}$ são  $[\lambda_1 v_1]_\mathcal{B} = \{\lambda_1, 0, 0, \cdots, 0\}$.

