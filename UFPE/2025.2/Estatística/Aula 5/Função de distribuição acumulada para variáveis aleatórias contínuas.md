Assim como definimos uma [[Função de distribuição acumulada para variáveis aleatórias discretas]] podemos também definí-la para [[Variável Aleatória Contínua|variáveis aleatórias contínuas]], essa definição é a seguinte:

$$
F(b) = P(X \leq b) =  \int_{-\infty}^b f(x)\,dx  
$$

Para essa função, valem as propriedades:

1. A função é crescente, ou seja $a \leq b \implies F(a) \leq F(b)$
2. $\lim\limits_{x \rightarrow \infty} F(x) = 1$ e $\lim\limits_{x \rightarrow -\infty} F(x) = 0$
3. $P(a \leq X \leq b) = F(b) - F(a)$
4. $F^\prime(x) = f(x)$, onde $f(x)$ é a função densidade de probabilidade