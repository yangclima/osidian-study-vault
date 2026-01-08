Agora que entendemos a [[Distribuição conjunta]] de [[Variável Aleatória Contínua|variáveis aleatórias]], podemos obter uma definição matematicamente robusta da independência dessas variáveis aleatórias. 

Sabemos que dois eventos $A$ e $B$ são independentes se e somente se:

$$
P(A\cap B) = P(A)P(B)
$$

Como, por definição, variáveis aleatórias associam valores aos resultados de experimentos e portanto valor aos eventos, então, dadas duas variáveis aleatórias $X$ e $Y$, estas são independentes se e somente se qualquer evento definido por $X$ for independente qualquer evento definido por $Y$, o que equivale a:

$$
F(x,y) = F_X(x)F_Y(y)
$$

Ou, de maneira equivalente (Para [[Variável Aleatória Discreta|variáveis aleatórias discretas]]):

$$
p(x_i,y_j) = p_X(x_i)p_Y(y_j)
$$

Ou, mesmo (Para variáveis aleatórias contínuas):

$$
f(x,y) = f_X(x)f_Y(y)
$$