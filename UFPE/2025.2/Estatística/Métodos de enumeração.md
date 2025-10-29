Tendo em vista que o cálculo da probabilidade de eventos parte dos conceitos [[Introdução a probabilidade|introdutórios da probabilidade]] no sentido de que sabemos que a probabilidade de um evento qualquer $A$ é definida como:
$$
P(A) =\frac{r}{k}
$$
Onde $r$ é a quantidade de eventos simples contidos em $A$ e $k$ é a quantidade total de eventos simples $\varepsilon$ do espaço amostral $S$ no qual $A$ está contido, torna-se evidente a necessidade de desenvolver métodos capazes de permitir o cálculo dessas quantidades de eventos simples mesmo para combinações complexas de eventos, esse métodos são denominados **Métodos de enumeração**.

# Regra da multiplicação
Se um procedimento $E_1$ pode ser executado de $n_1$ maneiras e um procedimento $E_2$ pode ser executado  de $n_2$ maneiras então um procedimento composto pela realização de $E_1$ **E ENTÃO** $E_2$ pode ser executado de $n_1 \cdot n_2$ maneiras, oque pode ser estendido para qualquer número de eventos consecutivos desde que estes sejam independentes entre si.
# Regra da adição
Se um procedimento $E_1$ pode ser realizado de $n_1$ maneiras e um procedimento $E_2$ pode ser realizado de $n_2$ maneiras, então um procedimento composto pela realização de $E_1$ **OU** $E_2$ pode ser realizado de $n_1 + n_2$ maneiras, oque pode ser estendido para qualquer número de eventos consecutivos desde que estes sejam independentes entre si.

# Permutação
Dado um conjunto de $n$ objetos, o número de formas diferentes nas quais podemos ordenar esses objetos é denominado número de permutações de $n$, discriminado por $_nP_n$ e que pode ser calculado da seguinte forma:
$$
_nP_n = n!
$$

# Arranjo
Dado um conjunto de $n$ objetos, selecionando $p$ desses objetos ($0 < p \leq n$), o número de formas nas quais podemos ordená-los é denominado número de Arranjos de $n$ objetos tomados $p$ a $p$, discriminado por $_nA_p$ e que pode ser calculado da seguinte maneira:
$$
_nA_p = \dfrac{n!}{(n-p)!}
$$

# Combinações
Dado um conjunto de $n$ objetos, podemos escolher dentro desse conjunto $p$ objetos de $C(n,p)$  formas diferentes, de tal forma que a ordem não importa nessa escolha, esse número de combinações pode ser determinado pela relação:
$$
\binom np = C(n,p) = \dfrac{n!}{p!(n-p)!}
$$

# Número de subconjuntos de um conjunto
Utilizando o conceito de combinação podemos calcular a quantidade de subconjuntos que um conjunto de $n$ elementos possui, obtendo o valor de $2^n$ subconjuntos, contando com o próprio conjunto e o conjunto vazio, esse resultado pode ser obtido por via do Binômio de Newton:
$$
(a+b)^n = \sum_{k=0}^n \binom{n}{k} a^{(n-k)}b^k
$$
Ao substituir $a$ e $b$ por 1, já que é fácil perceber que o número de subconjuntos possíveis é:
$$
\binom{n}{0}+\binom{n}{1}+\binom{n}{2}+ \cdots + \binom{n}{n}
$$
