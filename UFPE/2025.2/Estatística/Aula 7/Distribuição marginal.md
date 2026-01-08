Quando temos duas [[Variável Aleatória Contínua|variáveis aleatórias]] conjuntamente distribuídas, digamos $X$ e $Y$, muitas vezes queremos , ainda assim, considerar apenas uma delas por vez, nesse caso, queremos, por exemplo, descobrir a função massa ou densidade de probabilidade ou mesmo a função de probabilidade acumulada de $X$ ou de $Y$, nesse caso, teremos a **[[Função massa de probabilidade]] marginal** ou a **função densidade de probabilidade marginal** ou a **função de distribuição acumulada marginal**  da distribuição conjunta de $X$ e $Y$.

# Função massa de probabilidade marginal
Dadas duas [[Variável Aleatória Discreta|variáveis aleatórias discretas]] $X$ e $Y$, queremos então descobrir a **função massa de probabilidade marginal de $X$** ou seja, a função $p_X(x)$ que nos retorna a probabilidade $P(X=x)$, para cada valor de $x$ essa função assume um valor que equivale a soma da probabilidade de todos os pares ordenados $(X,Y)$ onde $X=x$, considerando então a nossa **tabela de probabilidade conjunta**, o valor de $p_X(x_i)$ seria obtido ao somar os valores da linha que corresponde ao valor $x_i$

![[est_004.png|center]]

Podemos então anotar, de forma muito conveniente, cada valor de $p_X(x)$ na **margem** direita da tabela, e considerando a função $p_Y(y)$, **função massa de probabilidade marginal de $Y$**, anotar de forma também conveniente cada valor de $p_Y(y)$ na **margem** inferior da tabela, então é daí que vem o **marginal**.

Formalmente, definimos então:

$$
p_X(x_i) = \sum_jp(x_i,y_j) \ \ \ \ \text{ e } \ \ \ \ p_Y(y_j) = \sum_ip(x_i,y_j)
$$

# Função densidade de probabilidade marginal
Sejam então $X$ e $Y$ duas [[Variável Aleatória Contínua|variáveis aleatórias contínuas]] com **função densidade de probabilidade** $f(x,y)$, utilizando a mesma lógica, as funções densidade de probabilidade marginal de $X$ e $Y$ são:

$$
f_X(x) = \int_c^df(x,y)dy \ \ \ \ \text{ e } \ \ \ \ f_Y(y) = \int_a^bf(x,y)dx
$$

# Função de distribuição acumulada marginal
Dada duas variáveis aleatórias $X$ e $Y$, contínuas ou discretas, temos, por definição que as **Funções de distribuição acumulada marginal** de $X$ e de $Y$ são:

$$
F_X(x) = \lim\limits_{y\ \to \ \infty} F(x, y) \ \ \ \ \text{ e } \ \ \ \ F_Y(y) = \lim\limits_{x\ \to \ \infty} F(x, y)
$$

