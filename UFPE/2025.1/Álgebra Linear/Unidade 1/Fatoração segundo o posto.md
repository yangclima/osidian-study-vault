A fatoração segundo o [[Escalonamento de matrizes#Posto e Nulidade de uma matriz|posto]] é uma forma de fatorar [[Matrizes]], i.e. descrever uma matriz $A$ como [[Multiplicação de matrizes|produto de uma matriz]] $X$ por uma outra matriz $C$.

No caso da **fatoração segundo o posto**, o objetivo é fatorar a matriz $A$ de tal forma que $X$ tenha $p$ colunas e $C$ tenha $p$ linhas,sendo $p$ o posto da matriz $A$, temos portanto $A = XC$.

O processo é simples: 
1. Primeiro [[Escalonamento de matrizes|escalone]] a matriz $A$ **anotando as operações elementares executadas para o escalonamento**, a matriz linha-equivalente obtida no escalonamento de $A$ é sua matriz $C$;
2. Pegue uma matriz identidade $I$ de ordem $n$ onde $n$ é a quantidade de linhas da matriz $A$ e execute sobre essa matriz identidade **o inverso** das operações elementares que foram utilizadas para escalonar $A$, **na ordem inversa**, ou seja, a última operação aplicada no escalonamento de de $A$  será a primeira aplicada na matriz identidade. Essa é sua matriz $X$;
3. Elimine as linhas nulas de $C$ e as respectivas colunas de $X$, ou seja, se eu eliminei a $i$-ésima linha de $C$, eliminarei também a $i$-ésima coluna de $X$;
4. Pronto, agora apenas escreva o produto $XC = A$;

A fatoração segundo o posto é uma maneira de economizar espaço de armazenamento, já que armazenar as matrizes $X$ e $C$ é muito menos custoso que armazenar a matriz $A$, desde que posto de $A$ sea muito menor que sua quantidade de linhas.