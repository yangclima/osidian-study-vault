Um problema que pode surgir e complicar o processo de aplicação da [[Análise Nodal]] são as chamadas **fontes de tensão flutuantes**, isto é, [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|fontes ideais de tensão]] que não estão conectados nem ao nó de referência (Terra) e nem a nenhuma outra fonte de tensão que esteja conectada ao terra.

O problema trazido por essas fontes é que, a sua [[Lei de Elemento]] não relaciona a tensão com a corrente, introduzindo uma complexidade que pode gerar sistemas lineares impossíveis, para resolver isso, usamos os chamados **super nós**, [[Terminologia|nós]] compostos no circuito que "envolvem" a fonte o que permite que cada fonte nos dê apenas uma tensão de nó.

Assim, temos o seguinte:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]
  \draw (0,3) node[left]{$e_2$} to[vsource, v=$V$, o-o] (0,0) node[left]{$e_1$};
  \draw (3,1.5) node{\huge $\rightarrow$};
  \draw (6,3) node[left]{$e_1 + V$} to[vsource, v=$V$, o-o] (6,0) node[left]{$e_1$};
\draw[dashed, green, thick, rounded corners] 
      ($(6,3)+(-1.5,0.5)$) rectangle ($(6,0)+(0.5,-0.5)$);
  \node[green, above] at (5.5, 3.5) {Super nó};
\end{circuitikz}
\end{document}
```

Perceba então que ao invés de lidar com duas tensões de nó, lidamos apenas com uma, e chamamos o conjunto formado pelo nó de tensão $e_1$ e o de tensão $e_1 + V$ de **super nó**.