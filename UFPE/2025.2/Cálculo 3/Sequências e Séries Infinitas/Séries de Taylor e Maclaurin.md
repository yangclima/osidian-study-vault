Agora que sabemos que algumas funções tem representações como [[Séries de Potências]] queremos agora, avaliar quais funções permitem esse tipo de representação e como podemos encontrá-las.

Suponha que $f(x)$ é uma função:

$$
f(x) = \sum_{n=0}^\infty c_n (x-a)^n = c_0 + c_1(x-a) + c_2(x-a)^2 + \cdots
$$

Queremos então, a priori, determinar em termos de $f$ os coeficientes da série que a representa, perceba então que tomando o valor de $f(a)$ como $x$ é igual a $a$ todos os termos da série serão nulos, com exceção de $c_0$, nesse caso:

$$
f(a) = c_0
$$

Encontrado o primeiro coeficiente da série, como faremos para encontrar o próximo? Bem, perceba que se [[Derivada|derivarmos]] a função $f$ obteremos:

$$
f^\prime(x) = c_1 + 2c_2(x-a) + 3c_3(x-a)^2 +\cdots
$$

Nesse caso, tomando $f^\prime(a)$ todos os termos serão nulos com exceção de $c_1$, nesse caso:

$$
f^\prime(a) = c_1
$$

Para encontrarmos $c_2$ poderíamos repetir o processo, obtendo então:

$$
f^{\prime\prime}(x) = 2c_2 + 6c_3(x-a) + \cdots
$$

Assim:

$$
f^{\prime\prime}(a) = 2c_2 \implies \dfrac{f^{\prime\prime}(x)}{2} = c_2
$$

Podemos então chegar então a conclusão de que o $n$-ésimo coeficiente da série que representa $f$ é dado por:

$$
c_n = \dfrac{f^{(n)}(a)}{n!}
$$

Onde $f^{(n)}$ é a $n$-ésima derivada de $f$, nesse caso chegamos ao seguinte teorema:

----
Se uma função $f$ tiver uma expansão (ou representação) em séries de potências em $a$, isto é:

$$
f(x) = \sum_{n=0}^\infty c_n(x-a)^n \ \ \ \ \ \ \ |x-a| < R
$$

Então os coeficientes dessa representação serão dados como o $n$-ésimo termo da seguinte [[Sequências|sequência]]:

$$
c_n = \dfrac{f^{(n)}(a)}{n!}
$$

Esta representação recebe então o nome de **Série de Taylor de $f$ em $a$** (Ou "em torno de $a$") e pode ser escrita como:

$$
f(x) = \sum_{n=0}^\infty \dfrac{f^{(n)}(a)}{n!}(x-a)^n \ \ \ \ \ \ \ |x-a| < R
$$

----

O caso especial onde $a =0$ ou seja para **Série de Taylor de $f$ em $0$** que equivale a:

$$
f(x) = \sum_{n=0}^\infty \dfrac{f^{(n)}(0)}{n!}x^n \ \ \ \ \ \ \ |x| < R
$$

E que aparece frequentemente em determinados problemas, nós apelidamos de **Série de Maclaurin**.

Como um exemplo podemos buscar a representação da função $f(x) = e^x$ como uma Série de Maclaurin, nesse caso, como a [[Derivadas de Ordem Superior|derivada de qualquer ordem]] dessa função será $f^{(n)}(x) = e^x$ e portanto $f^{(n)}(0) = e^0 = 1$ podemos escrever $f(x)$ como:

$$
f(x) = \sum_{n=1}^\infty \dfrac{x^n}{n!}
$$

Por fim, encontramos o raio de convergência dessa série através do [[Teste da razão]]:

$$
\lim\limits_{n\to\infty} \left|\dfrac{a_{n+1}}{a_{n}}\right| = \lim\limits_{n\to\infty} \left|\dfrac{x^{n+1}}{(n+1)!}\cdot\dfrac{n!}{x^{n}}\right| = \lim\limits_{n\to\infty} \dfrac{|x|}{n+1} = 0 < 1
$$

Concluímos então, via teste da razão que como o dado limite é $0$ qualquer que seja o valor de $x$ então a série é convergente em para qualquer $x \in \mathbb{R}$ e portanto o raio de convergência é $R = \infty$. 

Por fim, nosso objetivo é avaliar que condições uma função deve obedecer para que o valor da própria função seja igual a soma da sua representação  em série de Taylor, ou seja, assumindo que $f$ tem derivadas de todas as ordens, queremos avaliar a validade da igualdade

$$
f(x) = \sum_{n=0}^\infty \dfrac{f^{(n)}(a)}{n!}(x-a)^n
$$

Assim como para qualquer outra sequência convergente, a igualdade acima equivale a dizer que:

$$
f(x) = \lim\limits_{n\to\infty} T_n(x)
$$

Onde $T_n$ é a $n$-ésima soma parcial da série de Taylor de $f$ em $a$ também chamado de **polinômio de Taylor de $n$-ésimo grau de $f$ em $a$** (Caso $a = 0$ podemos também chamá-lo de **polinômio de Maclaurin**), ou seja:

$$
T_n(x) = \sum_{i=0}^n \dfrac{f^{(i)}(a)}{i!}(x-a)^i
$$

Considerando então

$$
R_n(x) = f(x) - T_n(x)
$$

O **resto** da série de Taylor de tal forma que 

$$
f(x) = R_n(x) + T_n(x)
$$

Vale então o seguinte teorema:

----
Se $f(x) = R_n(x) + T_n(x)$, onde $T_n(x)$ é o polinômio de Taylor de $n$-ésimo grau de $f$ em $a$ e

$$
\lim\limits_{n\to\infty} R_n(x) = 0
$$

Para $|x-a| < R$, então $f(x)$ é igual a soma da sua expansão em série de Taylor no intervalo $|x-a| < R$

----