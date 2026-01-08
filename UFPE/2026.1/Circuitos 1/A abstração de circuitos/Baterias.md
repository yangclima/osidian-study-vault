---
next: "[[Resistores Lineares]]"
prev: "[[Abstração de Circuitos]]"
---
O primeiro elemento real de circuitos que queremos analisar são as baterias que, em geral, são [[Células Galvânicas|fontes de energia derivadas de uma reação química interna]] e são representadas por:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz} 
    \draw
    % Desenha a bateria com terminais (o) e rótulos
    (0,0) to[battery1, l=$V$, o-o] (0,3);
    \draw
    (3,0) to[battery, l=$V$, o-o] (3,3);
\end{circuitikz}
\end{document}
```

As especificações importantes para esse tipo de dispositivo são a sua **tensão nominal**, **capacidade de armazenamento** e **resistência interna**.

A tensão nominal está intimamente ligada a reação química que libera a energia, assim, se um eletrodo tem um potencial padrão $1.5 \ V$ maior que o outro, o [[Potencial padrão de célula]] de $1.5 \ V$ e então a tensão nominal da bateria é $1.5 \ V$.

O segundo parâmetro relevante, a quantidade total de energia que a bateria armazena é medida em *Joules* pelo SI, mas é comum que seja visto em em *Watt-Hora* ou *Ampere-Hora*.

Quando conectada a uma carga [[Resistência|resistiva]], a bateria fornece uma [[Potência|potência]], medida em *Watts* dada por:

$$
p = VI
$$

A quantidade de energia fornecida num intervalo de tempo $[t_i,t_f]$, medida em *Joules* pode então ser calculada como:

$$
w = \int_{t_i}^{t_f} pdt
$$

Ou, caso a potência seja constante:

$$
w = p\Delta t
$$

Assim, a relação entre *Joules* e *Watt-hora* é obtida por:

$$
1 \ J \equiv 1 \ W\cdot s \implies 3600 \ J \equiv 1 \ W \cdot h
$$

Da mesma maneira, uma bateria que fornece uma corrente $A$ durante uma hora até descarregar tem uma capacidade de $A$ Ampere-Hora.

Para aumentar a tensão nominal em um circuito, podemos ligar baterias em série, aumentando também a capacidade de armazenamento, e para aumentar a capacidade sem mudar a tensão, podemos ligar baterias em paralelo.

