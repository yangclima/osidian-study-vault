Já vimos que podemos realizar [[Aritmética com variáveis aleatórias]], dessa maneira, se tivermos a definição de uma [[Variável Aleatória Contínua]] $X$ e sua [[Função de distribuição acumulada para variáveis aleatórias contínuas|função distribuição acumulada]] ou função densidade de probabilidade, podemos obter essa funções também para uma variável aleatória $Y$ definida em termos de $X$.

Isso pode ser feito através de uma mudança de variável, pro exemplo, se sabemos que $Y = X^2$ e $X\sim \text{U}(a,b)$, sabemos que $f(x) = 1/(b-a)$, nesse caso $x = \sqrt{y}$ e $dx = dy/(2\sqrt{y})$ e portanto $dx/(b-a) = dy/(2\sqrt{y}(b-a))$ e portanto $f_y(y) = 1/(2\sqrt{y}(b-a))$.

Isso também poderia ter sido feito manipulando a função distribuição de probabilidade acumulada: Sabemos que $F(x) = \dfrac{x - a}{b - a}$ e quanto a $Y$ podemos escrever: $F(y) = P(Y \leq y) = P(X^2 \leq y) = P(X \leq \sqrt{y})$ e portanto, temos: $F(y) = \dfrac{\sqrt{y} - a}{b - a}$  e por fim $f(y) = F^\prime(y) = 1/(2\sqrt{y}(b-a))$.

