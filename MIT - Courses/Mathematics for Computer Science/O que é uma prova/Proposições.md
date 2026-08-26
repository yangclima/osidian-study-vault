Uma proposição, um dos mais simples e fundamentais conceitos na matemática pode ser definido de maneira simples:

> Uma **proposição** é uma afirmação que pode ser classificada como verdadeira ou falsa

A princípio, restringir as afirmações que podem ser consideradas proposições àquelas que podem ser avaliadas como verdadeiro ou falso não parece surtir muito efeito ou limitar o conjunto de afirmações que podem ser classificadas como tal, no entanto, é essa restrição que evita que frases genéricas como "Bom dia!" ou "Como está você?" possam ser chamadas de proposições, além disso, impede que frases cuja veracidade varia circunstancialmente, como "São cinco horas!" de receber essa classificação.

Um ponto a atentar-se é que dizer que uma proposição sempre pode ser classificada como verdadeira ou falsa não implica dizer que seja fácil determinar a veracidade de qualquer proposição alegada, na verdade, há proposições que são estudadas há séculos e ainda não sabemos se são verdadeiras ou falsas.

Considere, a título de exemplo, a proposição "Para todo inteiro não negativo $n$, o valor de $n^2 +n+41$ é um número primo". Como primeiro impulso, poderíamos testar a função $p(n) ::= n^2 + n + 41$ (O símbolo $:\coloneqq$ significa "igual por definição")  para inúmeros valores, experimentar e verificar que de fato, para $n$ igual a 1, 2, 3, até 39, de fato, $p(n)$ é um número primo, só aí, dizer "Ok! Essa proposição é verdadeira", erro crasso! se testássemos mais um número, veríamos que $p(40) = 41\cdot 41$, um número não primo. A primeira lição que fica então é que, em geral, você não pode verificar a validade de uma alegação sobre um conjunto infinito utilizando uma amostra finita, não importa o quão grande ela seja, há, por exemplo, proposições falsas que só falham para números com mais de mil dígitos.

Para evitar as imprecisões e nuances da linguagem, os matemáticos criaram toda uma linguagem para expressar os tipos e formatos mais comuns de proposições, por exemplo, a última proposição que consideramos, poderia ser expressa como:

$$
\forall n \in \mathbb{N}. \ p(n) \text{ é primo}
$$

Nessa linguagem, $\forall$ significa "Para todo", $\in$ significa "em", "é membro de" ou "pertence" e $\mathbb{N}$ representa todo o conjunto de números inteiros não negativos ($\mathbb Z^+$ também poderia ser usado para representar o mesmo conjunto), enquanto o ponto antes de $p(n)$ serve para separar as orações da proposição.

No contexto da ciência da computação, a importância de estruturas como proposições vem de um importante processo nessa área: Avaliar e provar que um programa executará corretamente. Isso é importantíssimo em inúmeras aplicações e levou ao desenvolvimento de inúmeros métodos e abordagens nesse sentido.