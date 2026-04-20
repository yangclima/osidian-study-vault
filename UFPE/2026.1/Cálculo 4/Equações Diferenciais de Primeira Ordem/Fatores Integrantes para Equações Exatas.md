Em alguns casos, ao se deparar com uma [[Equações Diferenciais|EDO]] que não é [[EDO's Lineares de Primeira Ordem|Linear]],  [[Equações Separáveis|Separável]] e nem mesmo [[Equações Exatas|Exata]], podemos utilizar, tal qual no [[Método dos Fatores Integrantes]], um **fator integrante** conveniente $\mu(x,y)$ que permita transformar a equação em uma equação exata, conforme o seguinte procedimento:

$$Mdx + Ndy = 0$$
$$\mu Mdx + \mu Ndy = 0$$

e queremos então, para que a equação seja exata, que $(\mu M)_y = (\mu N)_x$ e então derivando essa igualdade, obtemos:

$$\mu_y M - \mu_xN + \mu(M_x-N_y) =0$$

Infelizmente, na maioria dos casos, resolver essas equação diferencial, que agora se trata de uma Equação Diferencial Parcial é tão quanto ou ainda mais difícil que resolver a EDO original, fazendo com que esse método seja útil apenas em casos especiais, isto é, nos casos em que $\mu$ é função somente de $x$ ou somente de $y$.

Para $\mu$ função somente de $x$, sabemos que $\mu_y =0$ e nesse caso:

$$-\mu_xN + \mu(M_x - N_y) = 0 \implies \mu_x  = \dfrac{(M_y - N_x)}{N}\mu$$

O que só vale se $\dfrac{(M_y - N_x)}{N}$ for função apenas de $x$, caso em que o fator integrante pode ser obtido resolvendo essa EDO.

Para $\mu$ função somente de $y$, sabemos que $\mu_x =0$ e nesse caso:

$$\mu_yM + \mu(M_x - M_y) = 0 \implies \mu_y  = \dfrac{(N_x - M_y)}{M}\mu$$

O que só vale se $\dfrac{(N_x - M_y)}{M}$ for função apenas de $x$, caso em que o fator integrante pode ser obtido resolvendo essa EDO.

Tendo então a equação original em mãos e também o fator integrante, basta então multiplicar a EDO por $\mu$ e resolvê-la através do mesmo método que usamos para as [[Equações Exatas]].