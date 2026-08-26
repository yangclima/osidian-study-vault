A linearidade das equações que regem o comportamento das redes resistivas (Também chamadas de redes lineares i.g. Redes compostas apenas por [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|Fontes de tensão/corrente]] e [[Resistores Lineares]]) possibilita a aplicação de poderosos  conceitos matemáticos da [[UFPE/2025.1/Álgebra Linear/Álgebra Linear|álgebra linear]] à análise desses circuitos, na [[Análise Nodal]] obtemos equações que, em geral, se encaixam nas seguintes duas definições: 

1. **Todos os termos do denominador possuem o mesmo sinal**
2. No numerador, cada termo é composto por um produto entre uma tensão de fonte e um fator resistivo (Condutivo), não aparecem produtos de tensões.

Assim, podemos matematicamente abstrair o fato de que a contribuição de cada fonte para uma variável de terminais, isto é, a diferença de potencial ou a corrente entre dois nós é independente das demais, o que abre um novo caminho para a análise de circuitos que possuem múltiplas fontes de tensão ou corrente.

A ideia é então calcular separadamente a contribuição de cada fonte, o que significa matematicamente tomar uma fonte por vez e substituir as demais por $0$, mas o que isso significa em termos de circuitos? 

1. Substituir uma fonte de tensão por $0$ significa zerar a [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|diferença de potencial]] no ramo na qual ela pertence, isto é, substituí-la por um curto-circuito.
2. Substituir uma fonte de corrente por $0$ significa zerar a [[Corrente]] no ramo a qual ela pertence, isto é, substituí-la  por um circuito aberto.

Usando essas ideias, podemos calcular as variáveis de ramo num circuito somando as contribuições individuais de cada fonte.

Considere, por exemplo, o seguinte circuito:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[V=$V_1$, invert] (3,3) 
      to[R=$R_3$] (6,3) 
      to[I<=$I$, invert] (6,0) 
      to[R=$R_4$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[V=$V_2$, *-*] (3,3);

\node[above=2pt] at (3,3) {$e_1$};
\node[below=2pt] at (3,0) {$e_2$};

\end{circuitikz}
\end{document}
```


Para considerar a tensão entre $e_1$ e $e_2$, consideremos uma fonte por vez, começando pela fonte $V_1$ e substituindo as demais por $0$, temos então o sub circuito:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[V=$V_1$, invert] (3,3) 
      to[R=$R_3$] (6,3);
      
\draw 
(6,0) to[R=$R_4$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[short, *-*] (3,3);

\node[above=2pt] at (3,3) {$e_1$};
\node[below=2pt] at (3,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Assim, a tensão entre os nós devido a $V_1$ é $0$.

Considerando então $V_2$, temos:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[short, invert] (3,3) 
      to[R=$R_3$] (6,3);
\draw
(6,0) to[R=$R_4$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[V=$V_2$, *-*] (3,3);

\node[above=2pt] at (3,3) {$e_1$};
\node[below=2pt] at (3,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Assim, a tensão entre os nós devido a $V_2$ é igual a $e_2 - e_1 = V_2$.

Por fim, considerando então $I$, temos:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american,scale=1.5]

\draw
(0,0) to[R=$R_1$] (0,3) 
      to[short, invert] (3,3) 
      to[R=$R_3$] (6,3) 
      to[I<=$I$, invert] (6,0) 
      to[R=$R_4$] (3,0) 
      to[R=$R_2$] (0,0);

\draw (3,0) to[short, *-*] (3,3);

\node[above=2pt] at (3,3) {$e_1$};
\node[below=2pt] at (3,0) {$e_2$};

\end{circuitikz}
\end{document}
```

Assim, devido a $I$ a diferença de tensão entre os nós é $0$.

Somando as contribuições, como era de se esperar, a diferença de tensão entre os dois nós é igual a $V_2$ o que era de se esperar pelo nosso estudo a cerca de [[Fontes de tensão flutuantes]].

O teorema da superposição pode ser então enunciado como:

> Numa rede linear como um número de fontes independentes, uma tensão entre nós pode ser obtida somando as tensões dos sub circuitos onde cada fonte está agindo sozinha com todas as outras definidas como $0$.

Esse teorema é então uma ferramenta poderosa na análise de circuito com múltiplas fontes, por que analisando o circuito com uma única fonte podemos usar com facilidade de artefatos como o [[Método Intuitivo de Análise de Circuitos]] ou os [[Divisores de Tensão e Corrente]].

Por outro lado, para analisar circuitos com [[Fontes dependentes]] não podemos substituir essas fontes por curto circuitos ou por circuitos abertos, nesse caso, deveremos analisar o sub circuito de cada fonte independente mantendo as fontes dependentes no circuito, o que, em geral, é mais complicado que aplicar outros métodos como [[Análise Nodal]] ou [[Análise de malha]]. 

