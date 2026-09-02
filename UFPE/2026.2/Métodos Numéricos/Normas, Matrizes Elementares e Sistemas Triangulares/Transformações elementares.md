Dada uma[[Definições e propriedades de Matrizes| matriz]] $A$, as seguintes operações sobre $A$ são denominadas de **operações elementares**:

1. Multiplicação de uma linha ou coluna por um número real $\alpha \neq 0$
2. Permuta de duas linhas ou de duas colunas
3. Adição do produto de uma linha por um número real a outra linha, ou adição do produto de uma coluna por um número real a outra coluna

Essas operações podem ser representadas por meio das chamadas **matrizes elementares**:

- **Multiplicação de uma linha (coluna) por um escalar $\alpha \neq 0$:** é efetuada multiplicando a matriz à esquerda (direita) por uma matriz elementar $E_\alpha$, que é a matriz identidade com o elemento da diagonal $e_{ii} = \alpha$, onde $i$ é o índice da linha (coluna) alterada.
- **Permutação de duas linhas (colunas):** mais especificamente da $i$-ésima pela $j$-ésima, é realizada multiplicando a matriz à esquerda (direita) por uma matriz elementar $E_{ij}$, que corresponde à matriz identidade com as linhas (colunas) $i$ e $j$ trocadas entre si.
- **Adição do produto de uma linha $i$ por $\alpha$ à linha $j$:** pode ser feita multiplicando a matriz à esquerda por uma matriz elementar $E$ que corresponde à matriz identidade com o elemento $e_{ji}$ substituído por $\alpha$. _(Nota: se a operação for feita nas **colunas**, adicionando o produto da coluna $i$ por $\alpha$ à coluna $j$, multiplica-se a matriz à direita por uma matriz elementar com o elemento $e_{ij} = \alpha$)._

A construção das matrizes elementares pode ser sintetizada da seguinte forma: tome a matriz identidade de mesma dimensão da matriz a ser operada e aplique a ela a operação elementar desejada. Como resultado, obtém-se uma matriz elementar $E$ que:

1. Ao **pré-multiplicar** $A$ ($E \times A$), aplica sobre as **linhas** de $A$ a mesma operação realizada nas linhas da identidade.
2. Ao **pós-multiplicar** $A$ ($A \times E$), aplica sobre as **colunas** de $A$ a mesma operação realizada nas colunas da identidade.

Assim, chamamos a operação de uma matriz $A$ e uma matriz elementar $E_i$ dada por $E_iA$ de **operação elementar de linha** e a operação $AE_i$ de **operação elementar de coluna**.

Uma das principais características e propriedades dessas matrizes é que elas podem [[Matriz Inversa|invertidas]] facilmente, para inverter $E_\alpha$, simplesmente elevamos o elemento $\alpha$ a $-1$, por outro lado, para inverter $E$ (Adição do produto de uma linha $i$ por $\alpha$ à linha $j$) trocamos o sinal de $\alpha$ e, por último, para $E_{ij}$ a sua matriz inversa é ela mesma.

Vale notar também que podemos combinar diversas operações elementares simplesmente multiplicando várias matrizes elementares obtendo uma combinação sequencial das operações.