Assim como calculamos a [[Normas de Vetores]], podemos também pensar num análogo de comprimento para [[Definições e propriedades de Matrizes|matrizes]], esse análogo é uma extensão da norma euclidiana chamada de **Norma de Frobenius**, definida da seguinte forma:

$$||A||_F = \left(\sum_{i=1}^m\sum_{j=1}^n|a_{ij}|^2\right)^{1/2} = (Tr(A^*A))^{1/2}$$

Sendo $A^*$ a matriz $A$ transposta e conjugada o que equivale a $A^T$ quando a matriz tem apenas números reais.

Uma outra abordagem para calcular esse "comprimento" é assumir $A$ como sendo um [[Transformações lineares|operador]] que transforma um vetor $x$ em um vetor $Ax$, assim, seu tamanho pode ser relacionado a o quando $A$ amplia $x$, isto é, seu tamanho pode ser relacionado ao tamanho de $Ax$ relativo a $x$, ou seja:

$$||A||_p = \max_{x\neq 0} \frac{||Ax||_p}{||x||_p} \equiv \max_{||x||_p=1}||Ax||_p$$

Como essa taxa de ampliação $||Ax||_p/||x||_p$ é obtida a partir da norma de vetor, dizemos que a norma $p$ das matrizes é induzida pela norma $p$ dos vetores, das normas $p$, duas tem o cálculo muito simples, definidas a seguir:

$$||A||_1 = \max_{1\leq j\leq n}\sum_{i=1}^m|a_{ij}|$$
$$||A||_\infty = \max_{1\leq i\leq m}\sum_{j=1}^n|a_ij|$$

Sendo então a norma-$l_1$ o valor máximo dentre as somas dos módulos dos elementos em cada coluna e a norma-$l_\infty$ o valor máximo dentre as somas dos módulos dos elementos em cada linha. 

Para o caso $p=2$, a norma da matriz é chamada de **Norma espectral**, correspondendo ao maior valor singular de $A$, ou seja, a raiz quadrada do maior [[Autovalores e autovetores|autovalor]] da matriz $A^*A$:

$$||A||_2 = \sqrt{\lambda_{max}(A^*A)}= \sigma_{max}(A)$$
 
Para qualquer norma $p$ de matrizes, valem as propriedades: 

1. $||A|| \leq 0$ e $||A|| =0$ se e somente se $A = 0$
2. $||\alpha A|| = |\alpha|||A||$ para todo $\alpha \in \mathbb C$ (Para todo $\alpha$ [[Números Complexos|complexo]]) e $A\in \mathbb C^{m\times n}$
3. $||A+B|| \leq ||A|| + ||B||$
4. $||Ax|| \leq ||A||||x||$
5. $||1|| = 1$
6. $||AB||\leq ||A||||B||$