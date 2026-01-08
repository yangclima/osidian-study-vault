Uma **Série de potências** é uma [[Séries|série]] da forma:

$$
\sum_{n=0}^\infty c_n x^n = c_0 + c_1x + c_2x^2 + \cdots
$$

Onde $x$ é uma variável e $c_n$ são constantes chamadas de **coeficientes da série** de tal forma que para cada $x$ fixado um série de potências é um série de constantes que podemos [[Estratégias para testes de séries|avaliar com respeito a sua convergência ou divergência]], de maneira que esta série pode convergir para certos valores de $x$ e divergir para outros.

A soma das séries de potências é então uma função $f(x)$ tal que

$$
f(x) = c_0 + c_1x + c_2x^2 + \cdots
$$

Cujo domínio é o conjunto dos valores de $x$ para os quais a série converge.

De forma mais geral, a série da forma

$$
\sum_{n=0}^\infty c_n (x-a)^n = c_0 + c_1(x-a) + c_2(x-a)^2 + \cdots
$$

É chamada de **série de potências em $(x-a)$** ou mesmo **série de potências centrada em $a$** ou **série de potências em torno de $a$**. Para estas séries, vale  o teorema:


---
Para dada série de potências $\sum_{n=0}^\infty c_n (x-a)^n$ existem três possibilidades:

1. A série converge apenas quando $x = a$
2. A converge para qualquer valor de $x$
3. Existe um número real positivo $R$ tal que a série converge desde que $|x-a|<R$ e diverge para $|x-a|>R$

----

No caso da terceira possibilidade $R$ é chamado de **raio de convergência** e o **intervalo de convergência** da série de potências é o intervalo $(a-R, a+R)$ para o qual, qualquer que seja o $x$ pertencente a tal intervalo a série é convergente para esse valor de $x$.

Em geral, o [[Teste da razão]] ou, às vezes, o [[Teste da raiz]] deve ser utilizado para avaliar o **raio de convergência** $R$ da série.

Para certas aplicações, é interessante que possamos representar funções através de séries de potências, por exemplo:

$$
f(x) = \dfrac{1}{1-x} = 1 + x + x^2 + \cdots = \sum_{n=0}^\infty x^n
$$

Um conclusão imediata já que esta série é bastante conhecida por nós, uma [[Séries Notáveis#Série geométrica|série geométrica]]. 

No caso de um série de potências, a sua soma é então uma função da forma $f(x) = \sum c_n(x-a)^n$ cujo  domínio é o **intervalo de convergência** da série, nesse caso, poderíamos então realizar operações como a [[Integral Indefinida|integração]] e a [[Derivada|derivação]] dessas funções? A resposta é sim, isso pode ser feito através da **derivação e integração termo a termo** e vale o seguinte teorema:

----
Se a série de potências f(x) = $\sum c_n(x-a)^n$ tiver um raio de convergência $R >0$ então a função $f$ definida como

$$
f(x) = \sum_{n=0}^\infty c_n(x-a)^n
$$

É derivável e portanto contínua no intervalo $(a-R, a+R)$ e vale que:

$$
f^\prime(x) = \sum_{n=0}^\infty nc_n(x-a)^{n-1}
$$

$$
\int f(x)dx = C + \sum_{n=0}^\infty \dfrac{c_n(x-a)^{n+1}}{n+1}
$$

----
