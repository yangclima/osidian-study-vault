Chamamos de **Vetor** uma [[Definições e propriedades de Matrizes|matriz]] coluna, isto é, uma matriz $A\in \mathbb{R}^{n\times 1}$ é geralmente chamada de vetor e geralmente designamos essas estruturas por letras minúsculas, ou seja,  $A = a$ e $a\in \mathbb R^n$. 

As principais operações envolvendo vetores são:

# Operações entre vetores
## Adição de vetores
Dados dois vetores $x\in \mathbb R^n$ e $y\in \mathbb R^n$ definimos a **adição de vetores** como

$$z = x+ y\implies z_i = x_i + y_i \ \ \ \ i=1,2,3,\cdots, n$$

Trata-se de uma operação comutativa (i.e. $x+y = y+x$) e associativa (i.e. $x+(y+z)= (x+y)+z$) cuja [[Complexidade de Algoritmos|complexidade]] é de $\mathcal{O}(n)$.

## Produto de vetor por escalar
Dados $x\in \mathbb R^n$ e $\alpha \in \mathbb R$ definimos o **produto de vetor por escalar** como

$$y = \alpha x\implies y_i = \alpha y_i \ \ \ \ i=1,2,3,\cdots, n$$

Trata-se de uma operação cuja [[Complexidade de Algoritmos|complexidade]] é de $\mathcal{O}(n)$.
## Produto escalar de vetores
Dados dois vetores $x\in \mathbb R^n$ e $y\in \mathbb R^n$ definimos o **produto escalar de vetores**, normalmente designado por $x\cdot y$ ou $\langle x,y \rangle$ como

$$c = \langle x,y \rangle =  x^Ty\implies c\in \mathbb R;\ \ \ c = \sum_{i=1}^n x_iy_i$$

Trata-se de uma operação comutativa (i.e. $x\cdot y = y \cdot x$) e associativa (i.e. $x\cdot(y\cdot z)= (x\cdot y)\cdot z$) cuja [[Complexidade de Algoritmos|complexidade]] é de $\mathcal{O}(n)$.
## Produto externo de vetores
Dados dois vetores $x\in \mathbb R^n$ e $y\in \mathbb R^n$ definimos o **produto externo de vetores**, como

$$z =  xy^T\implies z\in \mathbb R^{n\times n};\ \ \ z_{ij} = x_iy_j$$

Trata-se de uma operação que tem como resultado uma [[Matrizes|matriz]] quadrada singular cujo posto é sempre $1$ desde que $x\neq 0$ e $y\neq 0$ e cuja complexidade é $\mathcal O(n^2)$.
## Produto de vetor elemento a elemento
Dados dois vetores $x\in \mathbb R^n$ e $y\in \mathbb R^n$ definimos o **produto de vetores elemento a elemento**, como

$$z = x.*y \implies z_i = x_iy_i; \ \ \ \ i=1,2,3,\cdots,n$$

Trata-se de uma operação não conforme que não está definida formalmente na álgebra matricial mas que é importante computacionalmente, representando, por exemplo, o produto de uma matriz diagonal por um vetor (Desde que o vetor operado seja um vetor com os elementos da diagonal da matriz) com complexidade $\mathcal O(n)$.
## Operação SAXPY
Dados dois vetores $x\in \mathbb R^n$ e $y\in \mathbb R^n$ definimos o **a operação SAXPY (Sum of Alpha X plus Y)**, com base nas operações previamente definidas, como:

$$z = \alpha x + y \implies z_i = \alpha x_i+y_i$$

Trata-se de uma operação muito comum computacionalmente, representando, por exemplo uma correção de aproximação em alguns [[Algoritmos]] e cuja complexidade é $\mathcal O(n)$.

# Operações entre matrizes
## Adição de matrizes
Dadas duas matrizes $A\in \mathbb R^{n\times m}$ e $B\in \mathbb R^{n\times m}$ definimos a **adição de matrizes** como

$$Z = A+ B\implies z_{ij} = x_{ij} + y_{ij} \ \ \ \ i=1,2,3,\cdots, n; \ \ \ \ j=1,2,3,\cdots, m$$

Trata-se de uma operação comutativa (i.e. $A+B = B+A$) e associativa (i.e. $A+(B+C)= (A+B)+C$) cuja [[Complexidade de Algoritmos|complexidade]] é de $\mathcal{O}(n^2)$ (Para matrizes quadradas de dimensão $n\times n$).
## Produto de matriz por escalar
Dados uma matriz $A\in \mathbb R^{n\times m}$ e um escalar $\alpha \in \mathbb R$ definimos o **produto de matriz por escalar** como

$$Z = \alpha A \implies z_{ij} = \alpha x_{ij} \ \ \ \ i=1,2,3,\cdots, n; \ \ \ \ j=1,2,3,\cdots, m$$

Trata-se de uma operação cuja [[Complexidade de Algoritmos|complexidade]] é de $\mathcal{O}(n^2)$ (Para matrizes quadradas de dimensão $n\times n$).
## Produto de matriz por vetor
Dados uma matriz $A\in \mathbb R^{m\times n}$ e um vetor $b \in \mathbb R^{n}$ definimos o **produto de matriz por vetor** como

$$y = Ax \implies y_i = \sum_{j=1}^na_{ij}x_{j}$$

Note então que o $i$-ésimo elemento de $y$ equivale ao produto escalar da $i$-ésima linha de $A$ pelo vetor $x$, de forma similar, esse produto por ser escrito como uma soma das $m$ colunas de $A$ cada uma multiplicada por um fator $x_i$:

$$y = Ax \implies y = \sum_{j=1}^nx_iA_{i*}$$

Onde $A_{i*}$ representa a $i$-ésima linha de $A$. Essas duas formas de multiplicar uma matriz por um vetor pode ter um significativo impacto computacional a depender da forma de alocação de matrizes na memória na máquina específica em que o cálculo está sendo executado. A complexidade dessa operação é de $\mathcal O(n^2)$

## Produtos de matrizes
Dadas duas matrizes conformes (A quantidade de colunas de $A$ é igual a quantidade de linhas em $B$) $A \in \mathbb R^{m\times p}$ e $B\in \mathbb R^{p\times n}$ o **produto de matrizes** entre $A$ e $B$ resulta numa matriz $Z\in \mathbb R^{m\times n}$ e é definido por:

$$Z = AB\implies z_{ij} = \sum_{k=1}^pa_{ik}b_{kj}$$

A complexidade dessa multiplicação é de $\mathcal O(n^2)$ e temos como propriedades a associatividade (i.e. $A(BC) = (AB)C$) e a distributividade sobre a adição de matrizes (i.e. $A(B+C) = AB + AC$), além disso, temos que $(AB)^T = A^TB^T$ e que para qualquer matriz quadrada $A$, $A^TA$ e $AA^T$ são matrizes simétricas, além disso, temos que $AI = IA =A$ onde $I$ é a matriz identidade e que $A0 = 0A = 0$ onde $0$ é a matriz nula.

Ademais, temos que o produto $AD$ em que $D$ é diagonal equivale a multiplicar a $i$-ésima coluna de $A$ por $d_{ii}$ e que o produto $DA$ em que $D$ é diagonal equivale a multiplicar a $i$-ésima linha de $A$ por $d_{ii}$.

Como último fato, temos que, se particionarmos as matrizes $A$ e $B$ em blocos $A_{sr}$ e $B_{rt}$, isto é, em blocos iguais e conformes entre si (Partições de dimensões $s\times r$ e $r\times t$) dizemos que $A$ e $B$ são conformemente particionadas e podemos calcular seu produto utilizando cada partição como se fosse um elemento da matriz e multiplicando os de forma equivalente.