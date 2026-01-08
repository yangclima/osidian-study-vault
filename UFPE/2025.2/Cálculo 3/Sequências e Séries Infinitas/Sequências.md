# Definição e Notação
Uma sequência é uma lista de números $a_1, a_2, a_3, \cdots, a_n, \cdots$ onde $a_1$ é primeiro termo, $a_2$ é o segundo, $a_n$ é o $n$-ésimo termo e assim por diante, numa sequência infinita, objeto de estudo do cálculo 3, todo número $a_n$ sempre terá um sucessor $a_{n+1}$.

Nesse sentido, definindo formalmente:

>Uma sequência é uma [[Função]] real que tem como domínio o conjunto dos inteiros positivos, ou seja:
>$$f: \mathbb{Z^+} \rightarrow \mathbb{R}$$

Denotamos uma sequência com a seguinte notação:

$$
\{a_n\}
$$

Usualmente, utilizamos entre chaves a regra que define a sequência. Por exemplo:

$$
\left\{\dfrac{n}{n+1}\right\} = \left\{\dfrac{1}{2},\dfrac{2}{3},\dfrac{3}{4},\cdots\right\}
$$

# Limite de uma sequência
Uma sequência $\{a_n\}$ tem [[Limite|limite]] $L$ e denotamos por:

$$
\lim\limits_{n\rightarrow \infty} a_n = L
$$

Se pudermos tornar os termos de $a_n$ tão próximos quanto quisermos de $L$ ao tomar $n$ suficientemente grande. Se este limite existe, dizemos que a sequência **converge**, caso contrário, dizemos que ela **diverge**.

Podemos definir isso formalmente da seguinte forma:

> Uma sequência $a_n$ tem limite $L$ e denotamos $\lim\limits_{n\rightarrow \infty} a_n = L$ se $\forall \varepsilon > 0$, $\exists N \in \mathbb{Z^+}$ tal que se $n > N$, então $|a_n - L| < \varepsilon$.

Além disso, podemos associar as propriedades do limite de uma função que tem como domínio os números reais a às propriedades do limite de um sequência, ou seja:

> Se $f$ é uma função $f: \mathbb{R} \rightarrow \mathbb{R}$, de tal forma que $f(n) = a_n$, se $\lim\limits_{n\rightarrow \infty} f(x) = L$ então $\lim\limits_{n\rightarrow \infty} a_n = L$.

Além disso, as propriedades que já conhecemos dos limites são válidas para os limites de sequências:

Se $\{a_n\}$ e $\{b_n\}$ e $\{c_n\}$ são sequências convergentes e $c$ é uma constante, valem as propriedades:

1. $\lim\limits_{n\rightarrow \infty} a_n + b_n = \lim\limits_{n\rightarrow \infty} a_n + \lim\limits_{n\rightarrow \infty} b_n$
2. $\lim\limits_{n\rightarrow \infty} a_n - b_n = \lim\limits_{n\rightarrow \infty} a_n - \lim\limits_{n\rightarrow \infty} b_n$
3. $\lim\limits_{n\rightarrow \infty} c\cdot a_n = c \cdot \lim\limits_{n\rightarrow \infty} a_n$
4. $\lim\limits_{n\rightarrow \infty} a_n \cdot b_n = \lim\limits_{n\rightarrow \infty} a_n \cdot \lim\limits_{n\rightarrow \infty} b_n$
5. $\lim\limits_{n\rightarrow \infty} \dfrac{a_n}{b_n} = \dfrac{\lim\limits_{n\rightarrow \infty} a_n}{\lim\limits_{n\rightarrow \infty} b_n}$, se $\lim\limits_{n\rightarrow \infty} b_n \neq 0$
6. $\lim\limits_{n\rightarrow \infty} a_n^c= (\lim\limits_{n\rightarrow \infty} a_n)^c$, se $c > 0$ e $a_n > 0$
7. Se $a_n \geq b_n \geq c_n$ para $n > n_0$ e $\lim\limits_{n\rightarrow \infty} a_n = \lim\limits_{n\rightarrow \infty} c_n = L$, então $\lim\limits_{n\rightarrow \infty} b_n = 0$ (O [[Teorema do confronto|Teorema do confronto]], daqui também decorre que se $\lim\limits_{n\rightarrow \infty} |a_n| = 0$ então $\lim\limits_{n\rightarrow \infty} a_n = 0$.

Além disso, se uma função $f$ contínua for aplicada aos termos de uma sequência convergente $a_n$ tal que $\lim\limits_{n\rightarrow \infty} a_n = L$, vale que:

$$
\lim\limits_{n\rightarrow \infty} f(a_n) = f(L)
$$
Ou seja, uma função contínua aplicada aos termos de uma sequência convergente gera uma nova sequência convergente.
# Sequências Crescentes e Decrescentes
Uma sequência pode ser classificada como:

1. Crescente: Se $a_n < a_{n+1}$, $\forall n \geq 1$
2. Decrescente: Se $a_n > a_{n+1}$, $\forall n \geq 1$

Se uma sequência for **Crescente** ou **Decrescente** ela é então classificada como uma sequência **Monótona**.
# Sequências Limitadas
Uma sequência $\{a_n\}$ é:

1. **Limitada superiormente** se existe $M$ tal que $a_n\leq M$, $\forall n \geq 1$ 
2. **Limitada Inferiormente** se existe $m$ tal que $a_n\geq m$, $\forall n \geq 1$
3. **Limitada** se for limitada superiormente e inferiormente

Vale que: Toda sequência **limitada** e **monótona** é convergente.

Um sequência notável, isso é, importante de se memorizar é a seguinte:

$$
\lim\limits_{n\to\infty} \left(1 + \dfrac{a}{n}\right)^n = e^a
$$
