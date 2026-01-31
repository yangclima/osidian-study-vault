---
next: "[[Convenção de Variáveis Associadas]]"
prev: "[[Baterias]]"
---
Em geral, qualquer material por onde passa uma [[Corrente]] oferece uma certa [[Resistência|resistência]] a sua passagem, os componentes eletrônicos pensados especificamente para oferecer essa resistência são chamados de **resistores**, a maioria deles, na condição de operação obedecem a **Lei de Ohm** sendo então chamados de **Resistores Lineares** para os quais se aplica a relação:

$$
v = iR
$$

Isto é, a [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]] ao longo desses elementos é proporcional a corrente que passa por eles por uma constante de proporcionalidade $R$ chamada de **Resistência**. Esses elementos são representados pelo seguinte símbolo:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw
(0,0) to[R=$R$, o-o] (3,0);

\end{circuitikz}
\end{document}
```

Dois casos limite importantes para os resistores são $R\to0$, chamado de **curto circuito** e $R \to \infty$ chamado de **circuito aberto**.

Apesar de chamarmos de **resistor linear**, a resistência $R$ não precisa ser fixa no tempo e de fato, é comum que devido ao aquecimento, durante a operação a resistência varie, assim, temos:

$$
v(t) = i(t)R(t)
$$

Existem também os resistores não lineares, aqueles que não segue uma relação linear entre sua tensão, corrente e resistência, mas, em geral, um resistor de dois terminais é um elemento que possui uma relação algébrica entre esses fatores.