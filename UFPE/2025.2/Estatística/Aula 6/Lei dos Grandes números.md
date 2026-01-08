Intuitivamente, sabemos que a média de muitas medições de uma mesma quantidade desconhecida tende a nos dar uma melhor estimativa que uma única medição, isso deriva, ainda intuitivamente, do fato de que o erro aleatório associado ao nosso experimento se cancela na média.

Para transformar essa intuição em algo preciso, utilizamos, primeiramente a chamada Lei dos Grandes Números (LdGN), que, inicialmente sem rigor matemático, nos diz que:

1. A média de muitas amostras independentes que seguem uma mesma distribuição é, com alta probabilidade, próxima da [[Esperança]] para essa distribuição.
2. O [[Histogramas|Histograma]] de densidade de muitas amostras independentes que seguem a mesma distribuição é, com alta probabilidade, visualmente próximo ao gráfico da [[Variável Aleatória Contínua|função densidade de probabilidade]] da distribuição.

Um fato que é interessante de se atentar, é que, apesar de dizer isso, a Lei dos Grandes Números nada nos diz sobre a qualidade dos nossos dados, por exemplo, se utilizarmos um instrumento mal calibrado ou com defeito, a Lei dos Grandes Números nos diz que, com alta probabilidade, nossos dados nos darão uma estimativa altamente precisa da coisa errada.

Formalmente, a LdGN nos diz:

> Se $X_1, X_2, X_3, \cdots, X_n$ são [[Variável Aleatória Discreta|variáveis aleatórias]] independentes e igualmente distribuídas (Seguem uma mesma distribuição de probabilidade) com média $\mu$ e [[Variância e Desvio Padrão|desvio padrão]] $\sigma$. Para cada valor $n$, seja $\overline X_n$ a média das primeiras $n$ variáveis, então, para qualquer $a > 0$, temos:
> $$\lim\limits_{n\rightarrow \infty} P(|\overline{X}_n - \mu| < a) = 1$$
> 

Ou seja, quanto o número $n$ de amostras tente ao infinito a probabilidade da média das amostras estar próxima a média da distribuição dessas amostras tende a $1$.
