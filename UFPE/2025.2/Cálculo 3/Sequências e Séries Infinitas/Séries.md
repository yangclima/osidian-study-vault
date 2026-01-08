Em geral, uma **série infinita**, ou apenas **série** é obtida ao somarmos os termos de uma [[Sequências|sequência infinita]] $\{a_n\}$ e a denotamos por:

$$
\sum\limits_{n=1}^\infty a_n \ \ \ \ \text{ou, simplesmente} \ \ \ \ \ \sum a_n
$$

Algumas vezes, estas séries apresentam o interessante caráter de que, quando somamos os seus termos, o valor obtido se aproxima de um valor finito, nesse caso, dizemos que temos uma série convergente, já que esta **converge** para um valor finito.

> Dada uma série $\sum\limits_{n=1}^\infty a_n$, denotamos por $s_n$ a sua $n$-ésima soma parcial
> $$s_n = \sum\limits_{i=1}^n a_i = a_1 + a_2 + \cdots + a_n$$
> assim, se a sequência $\{s_n\}$ for convergente, ou seja, $\lim\limits_{n\rightarrow\infty} s_n = s$, então a série $\sum a_n$ é dita convergente e dizemos que:
> $$\sum\limits_{n=1}^\infty a_n = a_1 + a_2 + \cdots + a_n = s$$
> e então a **soma da série** $\sum a_n$ é $s$. Caso a sequência $\{s_n\}$, por outro lado, for divergente, então a série é dita divergente.

# A série geométrica
Um exemplo importante são as chamadas séries geométricas, séries do tipo:

$$
\sum\limits_{n=1}^\infty a\cdot r^{n+1} = a + ar + ar^2 + \cdots
$$

Séries que apresentam a agradável propriedade de que se $|r| < 1$, a sua soma é dada por:

$$
\sum\limits_{n=1}^\infty a\cdot r^{n-1} = \dfrac{a}{1-r}
$$

Caso $|r| \geq 1$, então a série é divergente.

# Teste de divergência
Perceba que, para que se uma série $\sum a_n$ for convergente, a sequência $\{s_n\}$, das suas somas parciais precisa ser convergente, o que só  ocorre se $\{a_n\}$ convergir para $0$, assim, como para muitas séries é difícil obter uma expressão para a $n$-ésima soma parcial,  podemos utilizar o limite $\lim\limits_{n \rightarrow \infty} a_n$ como um teste a respeito da divergência de $\sum a_n$:

> Se $\lim\limits_{n \rightarrow \infty} a_n \neq 0$ então a série $\sum a_n$ é divergente

é importante notar que, nesse caso, a recíproca não é verdadeira, ou seja, $\lim\limits_{n \rightarrow \infty} a_n \neq 0$ prova que a série $\sum a_n$ é divergente, mas $\lim\limits_{n \rightarrow \infty} a_n = 0$ não prova que $\sum a_n$ é convergente.
# Propriedades das séries convergentes
Se $\sum a_n$ e $\sum b_n$ forem séries convergentes e $c$ for uma constante qualquer, as séries $\sum c\cdot a_n$, $\sum a_n + b_n$ e $\sum a_n - b_n$ também o serão e vale que:

1. $\sum c\cdot a_n = c \cdot \sum a_n$
2. $\sum a_n + b_n = \sum a_n + \sum b_n$
3. $\sum a_n - b_n = \sum a_n - \sum b_n$

Por fim, vale notar, que um número finito de termos não afeta a convergência/divergência de uma série, assim, se soubermos que $\sum\limits_{n=N+1}^\infty a_n$ converge, então, a série:

$$
\sum\limits_{n=1}^\infty a_n = \sum\limits_{n=1}^N a_n + \sum\limits_{n=N+1}^\infty a_n
$$

Também converge.

