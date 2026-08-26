# Tipos principais de matrizes
De forma simples, uma [[Matrizes|matriz]] é um arranjo retangular de valores da forma

$$
A = 
\begin{bmatrix}  
a_{11} & a_{12} & \cdots & a_{1n} \\
a_{21} & a_{22} & \cdots & a_{2n} \\
\vdots & \vdots & & \vdots \\
a_{m1} & a_{m2} & \cdots & a_{mn}\\
\end{bmatrix}
$$

Diz-se que uma matriz de $m$ linhas e $n$ colunas é uma **matriz $m\times n$** e pertence ao [[Espaços vetoriais|espaço vetorial]] $\mathbb{R}^{m\times n}$, ou seja, se uma matriz $A$ tem $m$ linhas e $n$ colunas dizemos que $A \in \mathbb{R}^{m\times n}$. Os principais tipos de matrizes são:

- **Matriz quadrada:** Uma matriz cujo número de linhas é igual ao número de colunas
- **Matriz linha:** Uma matriz que tem uma linha e $n$ colunas (Chamada por vezes de vetor linha)
- **Matriz coluna:** Uma matriz que tem uma coluna e $m$ linhas (Chamada por vezes de vetor)
- **Matriz diagonal:** Uma matriz quadrada onde todos os elementos $a_{ij}=0$ para todo $i\neq j$
- **Matriz escalar:** Uma matriz diagonal onde todos os termos não nulos são iguais a um escalar $k$
- **Matriz identidade:** É uma matriz escalar na qual todos os elementos diagonais são iguais a $1$, sendo esta o elemento neutro da multiplicação de matrizes, ou seja, para qualquer matriz $A$ quadrada vale que $AI = IA = A$ onde $I$ é a matriz identidade
- **Matriz nula:** Uma matriz quadrada ou não cujos termos são todos nulos, sendo então o elemento neutro da adição de matrizes, isto é, para uma matriz qualquer $A$ e uma matriz nula de mesma dimensão $O$, vale $A+ O = O + A = A$ e, desde que haja compatibilidade para a multiplicação $AO = 0$.
- **Matriz triangular inferior:** Uma matriz onde todos os elementos acima da diagonal principal são nulos, caso todos os não nulos sejam unitários (Iguais a $1$), diz-se que ela é uma matriz triangular inferior unitária
- **Matriz triangular superior:** Uma matriz onde todos os elementos abaixo da diagonal principal são nulos, caso todos os não nulos sejam unitários (Iguais a $1$), diz-se que ela é uma matriz triangular superior unitária
- **Matriz transposta:** Dizemos que $B \in \mathbb{R}^{n\times m}$ é a transposta de uma matriz $A \in \mathbb{R}^{m\times n}$, o que denotamos por $B = A^T$ se para todo os elementos, $b_{ij} = a_{ji}$.
- **Matriz simétrica:** Uma matriz quadrada $A$ é dita simétrica se ela é igual a sua transposta, ou seja, se ela satisfaz $A=A^T$.
Para toda matriz $A$ [[Definições e propriedades de Matrizes|quadrada]] existe um escalar $|A|$ denominado determinante, que possui as seguintes propriedades:

1. O determinante é nulo se qualquer linha ou qualquer coluna da matriz for completamente nula
2. Se permutarmos linhas ou colunas da matriz a magnitude de seu determinante não muda
3. Se permutamos duas linhas ou colunas consecutivas, o sinal do determinante é invertido
4. Se multiplicamos uma linha ou coluna qualquer por um escalar $k$ o determinante será também multiplicado por $k$, por isso, se a matriz tem dimensão $n$ vale que $|kA| = k^n|A|$.
5. Se pegarmos uma linha (coluna) e somarmos seu valor multiplicado por uma constante $k$ a uma outra linha (coluna) o valor do determinante não muda
6. Se $A$ e $B$ forem matrizes quadradas de mesma ordem vale que $|AB| = |A||B|$

# Menor
Chamamos de **menor** o [[Determinantes|determinante]] $|M_{ij}|$ da [[Matrizes|matriz]] formada pelas $n-1$ linhas e $n-1$ colunas restantes ao retirar de uma matriz $A$ sua $i$-ésima linha e $j$-ésima coluna, obtendo assim o "**menor do elemento $a_{ij}$**". 

# Cofatores
Assim, definimos agora o **cofator** $c_{ij}$ do elemento $a_{ij}$ como sendo o menor desse elemento tomado o sinal equivalente a $(-1)^{i+j}$, ou seja $c_{ij} = (-1)^{i+j}|M_{ij}|$. 

# Cálculo do determinante por expansão
Agora utilizando os cofatores, podemos calcular o determinante $A$ por expansão por linha ou coluna usando as relações:

1. **Expansão pela coluna $j$:** $$|A| = \sum_{i=1}^na_{ij}c_{ij}$$
2. **Expansão pela linha $i$:** $$|A| = \sum_{j=1}^na_{ij}c_{ij}$$
# Matriz adjunta
Chamamos de **Matriz adjunta** de $A$, $Adj(A)$, como sendo a transposta da matriz de cofatores, isso é, a transposta da matriz $B$ onde cada elemento $b_{ij}$ corresponde ao cofator $c_{ij}$ de $A$.

# Matriz singular
Dizemos que uma matriz $A$ é uma **matriz singular** se seu determinante é $0$, caso contrário, dizemos que ela é não singular, numa matriz singular nem todas as linhas (ou colunas) são linearmente independentes das outras.

# Matriz inversa
Dizemos que uma matriz $B$ é a inversa de uma matriz $A$, isto é, $B = A^{-1}$ se ela satisfaz a condição de que $AB = BA = I$, onde $I$ é a matriz identidade da ordem de $A$. A matriz inversa pode ser obtida 
usando a expressão (Desde que a seja não singular):

$$A^{-1} = \frac{Adj(A)}{|A|}$$

A inversa do produto matrizes satisfaz a relação:

$$(AB^{-1}C)^{-1} = C^{-1}BA^{-1}$$

# Traço da matriz
Dada uma matriz quadrada $A$, chamamos de **Traço de $A$**, a soma dos elementos de sua diagonal:

$$Tr(A) = \sum_{i=1}^na_{ii}$$
# Autovalores e Autovetores
Os [[Autovalores e autovetores|autovalores]] de uma matriz quadrada $|A|$ são as raízes do polinômio característico de $A$, definido como:

$$p_A(\lambda) = |\lambda I-A|$$

Se $A$ tem dimensão $n\times n$, então o polinômio $p_A(\lambda)$ é de grau $n$ e suas raízes $\lambda_1,\cdots \lambda_n$ são os $n$ autovalores de $A$, sendo eles todos distintos ou tendo multiplicidades.

O determinante e o traço de uma matriz estão relacionados com os autovalores pelas equações:

$$|A| = \prod_{i=1}^n\lambda_i$$
$$Tr(A) = \sum_{i=1}^n\lambda_n$$

Por outro lado, os autovetores de uma matriz $A$ são todos os vetores não nulos $v_i$ que satisfazem:

$$Av_i = \lambda_iv_i $$

