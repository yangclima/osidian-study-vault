Os sistemas [[Álgebra de Matrizes Triangulares|triangulares]], sistemas de equações compostos pela multiplicação de [[Definições e propriedades de Matrizes|matrizes triangulares]] e vetores são extremamente importantes na computação matricial já que muitos métodos de solução de [[Sistemas lineares|sistemas lineares]] gerais são estruturados sobre a ideia de reduzir o sistema a um ou mais problemas desse tipo.

Considere um sistema triangular inferior da forma $Lx = b$:

$$
\begin{bmatrix}
l_{11} & 0 & 0 &  \cdots & 0 \\
l_{21} & l_{22} & 0 & \cdots & 0 \\
l_{31} & l_{32} & l_{33} & \cdots & 0 \\
\vdots & \vdots & \vdots & \ddots & 0 \\
l_{n1} & l_{n2} & l_{n_3} & \cdots & a_{nn}
\end{bmatrix} 
\begin{bmatrix}
x_{1}  \\
x_{2} \\
x_{3} \\
\vdots \\
x_{n}
\end{bmatrix} =
\begin{bmatrix}
b_{1}  \\
b_{2} \\
b_{3} \\
\vdots \\
b_{n}
\end{bmatrix}
$$

Podemos encontrar nesse sistemas o valor de $x_i$ aplicando o processo conhecido como **substituição para a frente**, isto é:

$$x_i = \frac{1}{l_{ii}}\left(b_1 - \sum_{j=1}^{i-1}l_{ij}x_j\right)$$

De forma equivalente, um sistema triangular superior  $Ux = b$ dado por:

$$
\begin{bmatrix}
u_{11} & u_{12} & u_{13} &  \cdots & u_{1n} \\
0 & u_{22} & u_{23} & \cdots & u_{2n} \\
0 & 0 & u_{33} & \cdots & u_{3n} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0& 0 & 0 & \cdots & u_{nn}
\end{bmatrix} 
\begin{bmatrix}
x_{1}  \\
x_{2} \\
x_{3} \\
\vdots \\
x_{n}
\end{bmatrix} =
\begin{bmatrix}
b_{1}  \\
b_{2} \\
b_{3} \\
\vdots \\
b_{n}
\end{bmatrix}
$$

Pode ser resolvendo usando a chamada **substituição para trás**:


$$x_i = \frac{1}{u_{ii}}\left(b_1 - \sum_{j=i+1}^{n}u_{ij}x_j\right)$$