---
next: "[[Representação de sinais]]"
prev: "[[Componentes Ideais]]"
---
Do ponto de vista da análise de circuitos, a característica mais importante de um [[Componentes Ideais|componente]] é a relação entre [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]] e [[Corrente|corrente]] desse elemento, chamada **Lei de elemento** ou **Curva V-I** já que esta presenta um resumo do comportamento do componente no circuito e segue a [[Convenção de Variáveis Associadas]], assim, para um resistor de $0.5 \ \ohm$, por exemplo, a curva V-I é:

```tikz
\usepackage{amsmath,amssymb}
\usetikzlibrary{decorations.pathreplacing}
\begin{document}
\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[domain=-4:4]
  \draw[very thin,color=gray] (-4,-4) grid (4,4);

  \draw[->] (0,-4) -- (0,4) node[right] {$V$};
  \draw[->] (-4,0) -- (4,0) node[right] {$I$};
  
  \draw[color=orange] plot (\x,{0.5*\x});
 
\end{tikzpicture}
\end{document}
```

Já para uma fonte de tensão ideal de $2 \ V$ temos:

```tikz
\usepackage{amsmath,amssymb}
\usetikzlibrary{decorations.pathreplacing}
\begin{document}
\tikzset{every picture/.style={line width=0.75pt}} %set default line width to 0.75pt        

\begin{tikzpicture}[domain=-4:4]
  \draw[very thin,color=gray] (-4,-4) grid (4,4);

  \draw[->] (0,-4) -- (0,4) node[right] {$V$};
  \draw[->] (-4,0) -- (4,0) node[right] {$I$};
  
  \draw[color=orange] plot (\x,2);
 
\end{tikzpicture}
\end{document}
```
