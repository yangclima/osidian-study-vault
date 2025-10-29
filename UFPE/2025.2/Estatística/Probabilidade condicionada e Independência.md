Os conceitos de probabilidade que vimos até aqui na nossa [[Introdução a probabilidade]] estudam ou abordam probabilidade de tal forma que cada evento é visto de maneira separada, existem situações porém, em que a ocorrência de um evento acaba por influenciar na probabilidade de um evento seguinte, um caso comum ocorre, por exemplo, quando escolhemos itens ao acaso dentro de um conjunto sem  realizar nenhum tipo de reposição, nesse caso, perceba que cada sorteio modifica de certa forma o espaço amostral influenciando no próximo, partindo desse ponto, podemos definir o seguinte:

> Dados dois eventos $A$ e $B$ eventos de um espaço amostral $S$, $P(B|A)$ é a probabilidade de $B$ ocorrer, dado que $A$ ocorreu

Perceba que podemos chegar logicamente no valor de $P(B|A)$ pensando da seguinte maneira: Enquanto a $P(B)$ é a soma da probabilidade de cada evento simples que satisfaz $B$ dentro de $S$ dividido pela probabilidade de $S$ (Que, como sabemos, é $1$), $P(B|A)$ é a soma da probabilidade de cada evento simples que satisfaz $B$ dentro de $A$, estamos portanto, analisando a intersecção entre $A$ e $B$ com relação a todos os eventos possíveis dentro de $A$, portanto, $P(A \cap B)$ chegamos assim, à seguinte expressão:

$$
P(B|A) = \dfrac{P(A \cap B)}{P(A)}
$$

Que é válida, desde que $P(A) > 0$, e permite inferir uma importante característica a partir de sua reorganização: $P(A \cap B) = P(B|A) \cdot P(A)$, o que, muitas vezes, é chamado de **Teorema da multiplicação de probabilidades** e que pode ser estendido para $n$ eventos.

No intuito de utilizar essa definição para o cálculo de um evento simples qualquer $A$, introduzimos um novo conceito, as partições:

> Dizemos que os eventos $B_1, B_2, \cdots, B_k$ representam uma partição do espaço amostral $S$ quando as seguintes condições são satisfeitas:
>   a) $B_i \cap B_j = \varnothing$, para todo $i \neq j$
>   b) $\bigcup\limits_{i=1}^k B_i = S$
>   c) $P(B_i) > 0$, para todo $i$ 
>   

O que estamos fazendo basicamente é dividir o nosso espaço amostral em pedaços independentes, utilizando esse artifício, podemos escrever um evento de interesse $A$ qualquer, da seguinte forma:
$$
A = (A \cap B_1) \cup (A \cap B_2) \ \cup \ \cdots  \ \cup (A \cap B_k)
$$
como, pela definição de partição cada elemento $(A \cap B_i)$ é mutuamente excludente, podemos escrever $P(A)$ da seguinte maneira:
$$
P(A) = P(A \cap B_1) + P(A \cap B_2) \ + \ \cdots  \ + P(A \cap B_k)
$$

E pelo Teorema da multiplicação de probabilidades chegamos então ao seguinte:
$$
P(A) = P(A|B_1) \cdot P(B_1) + P(A|B_2) \cdot P(B_2) + \cdots + P(A|B_k) \cdot P(B_k)
$$
Denominado **Teorema da probabilidade total**, extremamente útil para calcular a probabilidade de $A$ dividindo o cálculo em varias etapas menores que partem da definição de que $B_i$ ocorreu.

Podemos utilizar ainda os instrumentos construídos até aqui para inferir um último teorema, o **Teorema de Bayes** também conhecido como **Fórmula da probabilidade das causas** que permite calcular a probabilidade de um evento $A$ ter se originado de um evento $B$ (e.g. Escolhendo-se um dentre dois dados, um  viciado e um não viciado, dado que o resultado foi $\{1,1\}$, qual a probabilidade de o dado escolhido ter sido o viciado), que pode ser escrito da seguinte forma:
$$
P(B_i|A) = \dfrac{P(A|B_i)P(B_i)}{\sum\limits_{j=1}^k P(A|B_j)P(B_j)}
$$
Uma ferramenta muito útil para modelar problemas desse tipo é o chamado **Diagrama de árvore** que permite visualizar mais facilmente os eventos e relações de interesse

![[est_001.png|center]]

A definição de eventos independentes é logicamente simples, dois eventos são independentes se um não influencia no outro, ou seja, sejam dois eventos independentes $A$ e $B$ a probabilidade de $A$ não deve ser alterada pela ocorrência de $B$, logo:
$$
P(A|B) = P(A) = \dfrac{P(A\cap B)}{P(B)} \implies P(A \cap B) = P(B)P(A)
$$
Essa é portanto a definição de eventos independentes:

> Sejam $A$ e $B$, dois eventos de um espaço amostral $S$, $A$ e $B$ são independentes se e somente se $P(A \cap B) = P(A)P(B)$

