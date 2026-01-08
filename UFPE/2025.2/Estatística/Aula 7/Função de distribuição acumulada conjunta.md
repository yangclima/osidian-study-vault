$Sejam $X$ e $Y$ duas [[Variável Aleatória Contínua|variáveis aleatórias]] conjuntamente distribuídas, nós denotamos por $(X\leq x, Y\leq y)$ o evento determinado pela validade das expressões $X\leq x$ e $Y \leq y$, o que nos lembra a [[Função de distribuição acumulada para variáveis aleatórias contínuas|Função de distribuição acumulada]] para $X$ e para $Y$, da mesma forma que fazemos para uma variável aleatória individual, definimos então a **função distribuição acumulada conjunta de $X$ e $Y$** como:

$$
F(x,y) = P(X\leq x, Y\leq y)
$$

# Distribuição acumulada conjunta de v.a.c's
Sejam $X$ e $Y$ [[Variável Aleatória Contínua|variáveis aleatórias contínuas]], de tal modo que $X$ assume valores no intervalo $[a,b]$ e $Y$ assume valores no intervalo $[c,d]$ e a função densidade de probabilidade conjunta de $X$ e $Y$ é $f(x,y)$, então a **função distribuição acumulada conjunta $X$ e $Y$** é então definida como:

$$
F(x,y) = P(X\leq x, Y\leq y) = \int_c^y\int_a^x f(u,v)\,du\,dv
$$

Além disso, conhecendo $F(x,y)$ podemos obter a [[Distribuição conjunta|função densidade de probabilidade conjunta]] $f(x,y)$ como:

$$
f(x,y) = \dfrac{\partial^2 F(x,y)}{\partial x \partial y}
$$
# Distribuição acumulada conjunta de v.a.d's
Sejam $X$ e $Y$ duas [[Variável Aleatória Discreta|variáveis aleatórias discretas]] com [[Função massa de probabilidade]] $p(x_i,y_j)$, então a **função de distribuição acumulada conjunta de $X$ e $Y$** é então definida como:

$$
F(x,y) = P(X\leq x, Y\leq y) = \sum\limits_{x_i \leq x}\sum\limits_{y_j \leq x} p(x_i,y_j)
$$

# Propriedades
As propriedades da Função de distribuição acumulada conjunta são  as seguintes (Válidas tanto para as v.a.c.'s quanto para as v.a.d.'s):

1. $F(x,y)$ é não decrescente, podendo ser então, em qualquer intervalo, crescente ou constante
2. $\lim\limits_{\substack{x\to -\infty \\[2pt] y\to -\infty}} F(x,y) = 0$
3. $\lim\limits_{\substack{x\to \infty \\[2pt] y\to \infty}} F(x,y) = 1$

