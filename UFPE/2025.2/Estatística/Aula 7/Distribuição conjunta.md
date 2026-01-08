Muitas vezes, estamos interessados em mais de uma [[Variável Aleatória Contínua|variável aleatória]] ao mesmo tempo, isto é, queremos entender a relação e comportamento conjunto entre múltiplas variáveis aleatórias, nesse caso, temos o que chamamos de **distribuição conjunta**.

# Distribuição conjunta de v.a.d's
O primeiro caso é aquele que temos uma distribuição conjunta de duas [[Variável Aleatória Discreta|variáveis aleatórias discretas]]:

Seja $X$ um v.a.d. que assume valores no conjunto $\{x_1,x_2, \cdots, x_n\}$ e $Y$ uma v.a.d. que assume valores no conjunto $\{y_1,y_2, \cdots, y_m\}$, então o par ordenado $(X,Y)$ assume valores no produto $\{(x_1,y_1), (x_1,y_2),\cdots, (x_n,y_m)\}$, nesse caso, podemos definir a **[[Função massa de probabilidade]] conjunta de $X$ e $Y$** como a função $p(x_i, y_j) = P(X=x_i \cap Y=y_j)$, ou seja, uma função que, que dado um valor $x_i$ e um valor $y_j$ fornece a probabilidade de que em um experimento $X$ assuma o valor $x_i$ ao mesmo tempo em que $Y$ assume um valor $y_i$.

Essa probabilidade conjunta pode ser organiza convenientemente em uma tabela, chamada de **tabela de probabilidade conjunta**:

![[est_003.png|center]]

A **função massa de probabilidade conjunta** tem como propriedades:
1. $0 \leq p(x_i,y_i) \leq 1$
2. $\sum\limits_{i=1}^n\sum\limits_{j=1}^m p(x_i,y_j) = 1$
# Distribuição conjunta de v.a.c's
O segundo caso é aquele em que temos uma distribuição conjunta de duas [[Variável Aleatória Contínua|variáveis aleatórias contínuas]]:

Seja $X$ uma v.a.c. que assume valores no intervalo $[a,b]$ e $Y$ uma v.a.c. que assume valores no intervalo $[c,d]$, então, o par ordenado $(X,Y)$ assume valores em $[a,b]\times [c,d]$, nesse caso, podemos definir a **Função densidade de probabilidade conjunta de $X$ e $Y$**  como a função $f(x,y)$ que fornece a densidade de probabilidade de $(x,y)$.

A **função densidade de probabilidade conjunta** tem as seguintes propriedades:

1. $0 \leq f(x,y)$
2. $\int\limits_c^d\int\limits_a^bf(x,y)dxdy = 1$

# Eventos
Lembre-se que um evento é um conjunto de resultados e que as variáveis aleatórias atribuem números a esses resultados, da mesma forma que definimos eventos para uma uma única variável aleatória como "$X \leq 1$" ou $Y > 3$, podemos definir eventos conjuntos, como por exemplo $X + Y > 3$ o que equivale ao conjunto dos pares ordenados $(x,y)$ tal que $x+y > 3$.

