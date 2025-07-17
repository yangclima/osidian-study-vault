Uma **transformação linear** é um tipo especial de [[Função]] onde o domínio e o contradomínio são espaços vetoriais reais. A notação utilizada é:
$$
T: V \rightarrow W
$$
Onde $V$ e $W$ são [[Espaços vetoriais]] e $T$ é um função, o que implica a unicidade de uma transformação linear, ou seja, cada vetor $V$ tem um único vetor imagem denotado por $w = T(v)$. 

> *Se uma transformação linear é definida como $T: V \rightarrow V$ ela pode ser chamada de operador linear*

Para que uma dada aplicação seja chamada de transformação linear ela precisa satisfazer duas propriedades:
1. Aditividade: $T(u + v) = T(u) + T(v)$
2. Homogeneidade: $T(\lambda v) = \lambda T(v)$ 

>Uma propriedade útil que pode ser derivada das definições acima é que uma transformação linear leva o vetor nulo de um espaço vetorial para o vetor nulo do outro, ou seja $T(0) = 0$.

# Núcleo
O núcleo de uma transformação linear $T: V \rightarrow W$ é o conjunto de todos os vetores $v \in V$ tais que $T(v) = 0$, ou seja:
$$
N(T) = \ker{\ T} = \{ v \in V /  T(v) = 0\}
$$
# Imagem
A imagem de uma transformação linear $T: V \rightarrow W$ é o conjunto formado por todos os vetores $u \in W$ que são vetores imagem de pelo menos um vetor de $V$, ou seja:
$$
I(T) = Im \ T = \{u \in W / T(v) = w, v \in V\}
$$
 