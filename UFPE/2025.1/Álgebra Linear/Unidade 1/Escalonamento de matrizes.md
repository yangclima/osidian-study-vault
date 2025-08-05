O escalonamento de uma [[Matrizes|matriz]] $A$ é o procedimento seguido através do uso das 3 operações elementares no objetivo de transformar essa matriz numa matriz linha-equivalente a ela que segue as seguintes definições:
1. Todas as linhas nulas estão abaixo das linhas não nulas
2. O primeiro elemento não nulo de uma linha sempre está a direita do primeiro elemento não nulo da linha acima
# Operações elementares
As 3 operações elementares que podem ser realizadas sobre uma matriz são:
- Multiplicar uma linha por um escalar $L_1 \rightarrow \lambda L_1$
- Soma uma linha a um múltiplo de outra $L_1 \rightarrow L_1 + \lambda L_2$
- Trocar uma linha de posição $L_1 \longleftrightarrow L_2$
Essas operações são chamadas de elementares pois sua utilização resulta numa matriz que é linha-equivalente a matriz inicial.
# Posto e Nulidade de uma matriz
O posto $p$ de uma matriz $A$ é a quantidade de linhas não nulas de uma forma escalonada de $A$, já sua nulidade é a quantidade de linhas nulas ou $n - p$ onde $n$ é a quantidade de linhas de $A$ e $p$ seu posto.
# Operações elementares em termos de produtos de matrizes
As Operações elementares feitas sob uma matriz podem ser descritas com o [[Multiplicação de matrizes|produto dessa matriz]] por uma **matriz elementar** $E$:
## Multiplicar uma linha por um escalar 
Multiplicar uma linha da matriz $A$ por um escalar $\lambda$, e. g. $L_1 \rightarrow \lambda L_1$, pode ser descrita como o produto por uma matriz quadrada $E$ pela matriz $A$, da seguinte forma:
$$
\begin{vmatrix}
\lambda \ \ 0 \ \ 0 \\
0 \ \ 1 \ \ 0 \\
0 \ \ 0 \ \ 1 \\
\end{vmatrix}
\times
A = B
$$
## Somar uma linha a um múltiplo de outra
Somar uma linha de $A$ a um múltiplo de outra linha, e. g. $L_1 \rightarrow L_1 + \lambda L_2$
pode ser descrita como um produto de uma matriz elementar $E$ na forma:
$$
\begin{vmatrix}
1 \ \ \lambda \ \ 0 \\
0 \ \ 1 \ \ 0 \\
0 \ \ 0 \ \ 1 \\
\end{vmatrix}
\times
A = B
$$
## Trocar uma linha de posição
Troca uma linha de $A$ de posição, e.g. $L_1 \longleftrightarrow L_2$, pode ser também descrita por uma multiplicação por uma matriz Elementar $E$:
$$
\begin{vmatrix}
0 \ \ 1 \ \ 0 \\
1 \ \ 0 \ \ 0 \\
0 \ \ 0 \ \ 1 \\
\end{vmatrix}
\times
A = B
$$
## União de várias operações
A matriz elementar não precisa representar apenas uma operação e pode representar um conjunto delas, a matriz elementar para operações numa matriz $A$ pode ser obtida executando numa matriz identidade $I$ de ordem $p$ onde $p$ é o número de linhas de $A$ as mesmas operações executadas sobre $A$.