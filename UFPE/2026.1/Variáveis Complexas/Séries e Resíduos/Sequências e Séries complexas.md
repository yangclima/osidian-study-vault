  Uma [[Sequências|Sequência]] complexa $\{z_n\}$ é, de forma análoga às séries reais, uma [[Funções Complexas|função]] que tem como domínio os números inteiros reais e como contradomínio o conjunto $\mathbb{C}$ [[Números Complexos]], ou seja, sua imagem é um subconjunto de $\mathbb{C}$.

Se existe um limite $L$ tal que para uma sequência $\{z_n\}$ é verdade que $\lim\limits_{z\to\infty}z_n = L$ dizemos que essa série é convergente, caso contrário, dizemos que ela é divergente.

Como critério para a convergência, adotamos:

> Uma série $\{z_n\}$ converge ao número complexo $L = a +ib$ se e somente se $Re(\{z_n\})$ convergir para $a$ e $Im(\{z_n\})$ convergir para $b$.

Uma [[Séries|Série]] complexa, por sua vez é uma soma infinita da forma

$$\sum_k^\infty z_k = z_1 + z_2 + z_3 + \cdots + z_n + \cdots$$

Dizemos que essa série é convergente se a sequência de termos parciais $\{z_n\}$ dada por

$$z_n = z_1 + z_2 + \cdots + z_n$$

For convergente, nesse caso, se essa sequência converge para $L$ dizemos que  a série converge a $L$.

Relembremos uma série muito especial que será particularmente útil nos nossos estudos de Variáveis Complexas:

>Uma [[Séries Notáveis#Série geométrica|série geométrica]] é uma série da forma $\sum_{k=1}^\infty az^{k-1}$, muito interessante, já que podemos escrever uma fórmula para a $n$-ésima soma parcial como sendo $\dfrac{a(1 - z^n)}{1-z}$ de modo que ela diverge para $|z|\geq1$ e converge para um valor $a/(1-z)$ para qualquer valor de $|z|<1$.

Duas deduções imediatas e importante a partir dessa série são:

$$\dfrac{1}{1-z} = 1 + z + z^2 + z^3 + \cdots$$

$$\dfrac{1}{1+z} = 1 - z + z^2 - z^3 + \cdots$$

As condições necessárias para a convergência das séries complexas são similares àquelas necessárias para a convergência de séries reais, por exemplo, o $\lim\limits_{n\to\infty}z_n$ tem que ser zero, ainda valem aqui os conceitos de [[Convergência absoluta e condicional]] e a série converge se convergir absolutamente valem também o [[Teste da raiz]] e o [[Teste da razão]].

Outra série importante é a [[Séries de Potências|série de potências]]:

> Uma série de potências complexa é uma série infinita da forma:
> $$\sum_{k=0}^\infty a_k(z-z_0)^k = a_0 + a_1(z-z_0) +a_2(z-z_0)^2 + \cdots$$
> Onde os coeficientes $a_k$ são constantes complexas, no caso acima, dizemos que se trata de uma **série de potências em $z-z_0$** ou **centrada em $z_0$** e $z_0$ é o ponto complexo denominado **centro da série**.

Assim como toda série de potências reais tem um intervalo de convergência, uma série de potências complexa tem um **raio de convergência**, isto é, sua convergência depende do módulo $|z-z_0|$ e da sequência $\{a_n\}$ dos coeficientes podendo ser nulo, convergindo apenas em $z = z_0$, tendo um raio finito $R$ de modo que a série converge para todos os pontos $z$ no interior de um círculo de raio $R$ centrado em $z_0$ (Região $|z-z_0| < R$) e pode ainda ter um raio de convergência infinito, convergindo para qualquer valor de $z$, entretanto, a série pode convergir para todos, nenhum ou alguns pontos da circunferência $|z-z_0| < R$.

A partir do teste da razão, concluímos que a convergência de uma série de potências depende apenas dos coeficientes $a_k$ de modo que:

1. Se $\lim\limits_{n\to\infty}\left|\dfrac{a_{n+1}}{a_n}\right| = L \neq 0$ o raio de convergência é $R = \dfrac{1}{L}$
2. Se $\lim\limits_{n\to\infty}\left|\dfrac{a_{n+1}}{a_n}\right| = L = 0$ o raio de convergência é $R = \infty$
3. Se $\lim\limits_{n\to\infty}\left|\dfrac{a_{n+1}}{a_n}\right| = \infty$ o raio de convergência é $R = 0$

Da mesma forma, para o teste da raiz:

1. Se $\lim_\limits{n\to\infty}\sqrt[n]{|a_n|} =L \neq 0$, então $R = 1/L$
