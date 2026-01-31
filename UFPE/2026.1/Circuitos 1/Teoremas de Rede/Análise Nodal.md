Atualmente, o nosso método básico de análise de circuito envolve a aplicação pura e direta da [[Lei de Kirchhoff das Tensões]] e da [[Lei de Kirchhoff das Correntes]] o que permite calcular as nossas variáveis de circuito através de [[Sistemas lineares]], entretanto, tome como exemplo o seguinte circuito:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_1$] (3,0)
to[R=$R_2$] (3,3) -- (0,3);

\draw
(3,0) --
(6,0) to[R=$R_3$] 
(6,3) -- (3,3);

\end{circuitikz}
\end{document}
```

Só nesse simples circuito, temos $2$ equações independentes provenientes da LKC e $2$ equações independentes provenientes de LKT, além das $7$ [[Lei de Elemento|Leis de elemento]], ou seja, uma sistema linear de $8$ equações que precisa ser resolvido, percebemos então que é essencial desenvolver métodos mais poderosos para resolver esse tipo de problema.

O primeiro método que veremos é a **Análise nodal** que baseia-se na [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|Diferença de potencial]] entre dois nós para encontrar as variáveis do circuito.

Lembre-se que para definir o potencial elétrico em um ponto do espaço, precisamos primeiro de uma referência, um ponto que consideramos como potencial $0$ e então, com base nessa referência é que mensuramos a diferença de potencial entre dois pontos e portanto a tensão entre eles que dada a devida lei de elemento nos dá também a corrente.

Definimos então a tensão de ramo, num [[Terminologia|ramo do circuito]] como sendo a diferença entre a tensão de nó do terminal positivo menos a tensão de nó do terminal negativo:

$$
v = v_+ - v_-
$$

A ideia é então definir um nó conveniente no nosso circuito que tomaremos como o nosso ponto de potencial $0$, também chamado de "terra" ou "*ground*" e simbolizamos por um T invertido, por exemplo:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_1$] (3,0)
to[R=$R_2$] (3,3) -- (0,3);

\draw
(3,0) --
(6,0) to[R=$R_3$] 
(6,3) -- (3,3);

\draw
(0,0) node[rground]{};

\end{circuitikz}
\end{document}
```

Assim, definimos que a **tensão de nó** no nó conectado ao terminal negativo da nossa [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|fonte de tensão]] é $0$ e que portanto a tensão no nó superior conectado ao terminal positivo da fonte deve ser $V$

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_1$] (3,0)
to[R=$R_2$] (3,3) -- (0,3);

\draw
(3,0) --
(6,0) to[R=$R_3$] 
(6,3) -- (3,3);

\draw
(0,0) node[rground]{};

\draw
(-0.2,3.2) node{$V$};

\draw
(3, -0.2) node{$e_2$};

\end{circuitikz}
\end{document}
```

E então, toda a parte superior do circuito deve possui a mesma tensão $V$, porém, queremos ainda encontrar as tensões do nó inferior, conectado ao resistores, denominada $e_2$ (Normalmente rotulamos com $e$ as tensões de nó).

Para encontrar $e_2$ escrevemos as equações de LKC para as correntes saindo do nó $e_2$ considerando a [[Convenção de Variáveis Associadas]] como designado na seguinte imagem:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource=$V$] 
(0,0) to[R=$R_1$, i^<=$i_1$, v<=$v_1$] (3,0)
to[R=$R_2$, i>_=$i_2$] (3,3) -- (0,3);

\draw
(3,0) --
(6,0) to[R=$R_3$, i>_=$i_3$] 
(6,3) -- (3,3);

\draw
(0,0) node[rground]{};

\draw
(-0.2,3.2) node{$V$};

\draw
(3, -0.2) node{$e_2$};

\end{circuitikz}
\end{document}
```

Temos então:

$$
i_1 + i_2 + i_3 = 0
$$

Porém, por convenção,  a corrente sempre entra no terminal positivo, que, nesse caso tem tensão $e_2$, dessa maneira, como $i = v/R$ para os [[Resistores Lineares]] e $v = v_+ - v_-$ temos:

$$
\dfrac{e_2 - 0}{R_1}  + \dfrac{e_2 - V}{R_2}  + \dfrac{e_2 - V}{R_3} = 0
$$

Ou, por simplicidade, usando a [[Condutância]] temos:

$$
e_2G1  + (e_2 - V)G_2 + (e_2 - V)G_3 = 0
$$

O que resolvemos como:

$$
e_2 = \dfrac{V(G_1+G_2)}{G_1+G_2 + G_3} = \dfrac{V \cdot R_1 (R_2 + R_3)}{R_1 R_2 + R_1 R_3 + R_2 R_3}
$$

Assim, podemos, usando as tensões de nó, encontrar qualquer corrente ou tensão no circuito, por exemplo, a tensão em $R_1$ é:

$$
v_1 = e_2 - 0 = \dfrac{V(G_1+G_2)}{G_1+G_2 + G_3} = \frac{V R_1 (R_2 + R_3)}{R_1 R_2 + R_1 R_3 + R_2 R_3}
$$

E a corrente é:

$$
i_1 = \dfrac{v_1}{R_1} = \dfrac{e_2 - 0}{R_1} = \frac{V (R_2 + R_3)}{R_1 R_2 + R_1 R_3 + R_2 R_3}
$$

O que pode ser feito para todos os outros elementos, perceba então que precisamos resolver uma única equação para descobrir todas as variáveis do nosso circuito.

Sintetizamos então o processo de análise nodal através dos seguintes passos:
1. Defina o seu nó de referência, onde assumiremos que $e = 0$ e simbolizaremos através de um $T$ invertido, escolher convenientemente o nó pode facilitar bastante o processo, prefira nós conectados ao máximo de elementos possível e de forma ainda mais importante, escolha nós que estejam conectados ao máximo de fontes de tensão.
2. Identifique então todos os outros nós onde a tensão é desconhecida rotulando-os, normalmente denotamos esses nós por $e_1, e_2, \cdots e_n$
3. Escreva as equações da [[Lei de Kirchhoff das Correntes]] para cada um dos nós de tensão desconhecida, para evitar erros, você pode assumir sempre que todas as correntes estão saindo do nó e tomar estas por positivas, assim, cada [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|Diferença de potencial]] poderá ser escrito como a tensão de nó do nó atual mesmo a tensão de nó do outro terminal, além disso, utilizar a [[Condutância]] dos [[Resistores Lineares]] ao invés de sua [[Resistência]] pode simplificar as coisas
4. Resolva as equações obtendo todas as tensões de nó que faltam.
5. Utilizando os valores obtidos, volte e utilize a [[Lei de Elemento]] de cada elemento para encontrar a tensão e a [[Corrente]] em cada elemento.

Algo interessante é que as expressões obtidas para as tensões de nó seguem sempre duas regras básicas:

1. Todos os termos do denominador possuem o mesmo sinal o que faz com que o denominador não possa ser zero para valores não nulos das condutância e portanto a tensão de nó não possa ter um valor infinito para valores finitos de tensões nas fontes.
2. No numerador, cada termo é composto por um produto entre uma tensão de fonte e um fator resistivo (Condutivo), não aparecem produtos de tensões.