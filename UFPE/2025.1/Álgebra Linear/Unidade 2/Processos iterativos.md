Dada um [[Transformações lineares|operador linear]] $L: \mathbb{R}^n \rightarrow \mathbb{R}^n$, descrito pela [[Matriz de transformação linear|matriz]] $A$ de ordem $n$ e um vetor inicial $x_0 \in \mathbb{R}^n$, uma sequência de vetores $x_1, x_2, \cdots, x_k$ é obtida por sucessivas aplicações do operador $L$:
$$
\begin{aligned}
x_1 &= Ax_0\\
x_2 &= Ax_1 = A^2x_0 \\
& \cdots \\
x_k &= Ax_{k-1} = A^{k-1}x_0
\end{aligned}
$$
Esses tipo de sequência é muito comum em aplicações da Álgebra Linear, principalmente para descrever processor físicos, químicos, sociais, biológicos... 

Em problemas como esse, se temos a seguinte condição satisfeita, onde $\lambda_i$ é o $i$-ésimo [[Autovalores e autovetores|autovalor]] de $A$:
$$
\lambda_1 = 1, |\lambda_j| < 1, \forall j\neq 1
$$

Então a sequência converge para um autovetor associado ao autovalor $\lambda_1$ numa velocidade que corresponde a velocidade onde $\lambda \rightarrow 0$, onde $\lambda$ é o segundo maior autovalor de $A$ em magnitude.