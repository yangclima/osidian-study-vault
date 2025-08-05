

A partir das condições que definem a possibilidade de uma vetor $v$ qualquer, ser um [[Autovalores e autovetores|autovetor]] referente a um [[Transformações lineares|operador linear]] $L$ definido por uma [[Matriz de transformação linear]] $A$, podemos concluir que $\lambda$ é um autovalor de $L$ se, e somente se, $\lambda$ for solução da seguinte equação em $t$:
$$
\det(tI_n - A) = 0
$$
O primeiro membro da equação é denominado **polinômio característico** de $A$, denotado por $c_A(A)$, porém, qualquer duas matrizes  semelhantes tem o mesmo polinômio característico, portanto:
$$
c_L(t) = \det{(tI_n - [L]_{\mathcal{B}}^{\mathcal{B}})}
$$
Conhecidos os autovalores podemos então encontrar os autovetores associados ao autovalor $\lambda$ como os vetores não nulos do espaço de anulamento descrito por:
$$
V_\lambda = \mathcal{N}(A - \lambda I_n)
$$
Denominado **autoespaço** correspondente a $\lambda$.

Como consequência do teorema fundamental da álgebra, qualquer polinômio de grau $n \geq 1$  e coeficientes reais ou complexos possui exatamente $n$ raízes reais ou complexas, contadas com possíveis repetições
$$
p(t) = a_n(t - \lambda_1)^{m_1}(t - \lambda_2)^{m_2}\cdots(t - \lambda_k)^{m_k}
$$
Onde $\lambda_1, \lambda_2, \cdots, \lambda_k$ são as raízes e $m_1, m_2, \cdots, m_k$ suas respectivas multiplicidades. 

Para o polinômio característico definimos para um autovalor (Raiz de $c_A(t)$) sua multiplicidade algébrica como a sua multiplicidade como raiz do polinômio e a sua multiplicidade geométrica como a dimensão do autoespaço associado a $\lambda$. Obtendo:

1. Se um operador $L$ é diagonalizável, então todas as raízes de $c_ A(t)$ são reais (Porém, ter todas as raízes reais não garante que $L$ é diagonalizável)
2. Se $\lambda$ é um autovalor real de $L$, sua multiplicidade geométrica é sempre menor ou igual a sua multiplicidade algébrica.