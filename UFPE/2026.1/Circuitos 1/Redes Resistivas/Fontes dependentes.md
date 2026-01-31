As [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|fontes de tensão e corrente]] que vimos até agora são fontes denominadas independentes, isto é, possuem valores de tensão ou corrente que são constantes ou com [[Fontes de Corrente Alternada|comportamento periódico]] independente, apesar disso, existem também outro tipo de fontes de [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]]/[[Corrente|corrente]] que por dependerem de outros parâmetros do circuito são denominadas **fontes de tensão/corrente dependentes**.

Isto é, fontes para quais o valor de saída apresentado depende de um outro valor de tensão ou corrente no circuito, estas fontes também são chamadas de **fontes controladas**, um exemplo é a chamada *Voltage Controlled Current Source* (**VCCS**) ou Fonte de corrente controlada por tensão, exibida na imagem abaixo:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american, scale=2]
\draw (3,0) node[above, green]{-} -- (0,0) to[cisource, l_={\color{green}$\ \ f(v_{IN})$}, invert, o-o] (0,3) to[short, i<=$i_{OUT}$] (3,3) node[below, green]{+};
\draw (-2, 0) node[above, green]{-} to[short, o-o] (-0.4, 0);
\draw (-2, 1.5) node[green]{$v_{IN}$};
\draw (3, 1.5) node[green]{$v_{OUT}$};
\draw (-2, 3) node[below, green]{+} to[short, o-o, i=$i_{IN}$] (-0.4, 3);
\end{circuitikz}
\end{document}
```


A característica chave dessas fontes é que a corrente fornecida é uma função da tensão $v_{IN}$, isto é $i_{OUT} = f(v_{IN})$.

Um fator importante de levar em conta é que assumimos, por idealização, que o controle de uma dessas fontes não requer o fornecimento de nenhuma energia, isto é, nenhuma potência esta sendo fornecida aos terminais de controle da fonte.

Um tipo de VCCS muito comum são as chamadas **fontes dependentes lineares** que tem como [[Lei de Elemento]] equações do tipo:

$$
i_{OUT} = g\cdot v_{IN}
$$

Onde $g$ é uma constante chamada de **transcondutância** da fonte e tem unidades de [[Condutância]]. 

Outros tipos de fontes dependentes são a CCVS (*Current Controlled Voltage Source*), CCCS (*Current Controlled Current Source*) e VCVS (*Voltage Controlled Voltage Source*), para  o caso linear dessas últimas duas chamamos a constante de proporcionalidade na lei de elemento de **taxa de transferência ou razão de transferência**. 

Por exemplo: A seguinte fonte é uma CCVS cuja lei de elemento é dada por $v_{OUT} = f(v_{IN}) = \mu \cdot v_{IN}$, ou seja, a tensão fornecida pela fonte é função da tensão de entrada da fonte e $\mu$ é chamada de *taxa de transferência de tensão*

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american, scale=2]
\draw (3,0) node[above, green]{-} -- (0,0) to[cvsource, l_={\color{green}$\ \mu \cdot v_{IN}$}, invert, o-o] (0,3) to[short, i<=$i_{OUT}$] (3,3) node[below, green]{+};
\draw (-2, 0) node[above, green]{-} to[short, o-o] (-0.4, 0);
\draw (-2, 1.5) node[green]{$i_{IN}$};
\draw (3, 1.5) node[green]{$v_{OUT}$};
\draw (-2, 3) node[below, green]{+} to[short, o-o, i=$i_{IN}$] (-0.4, 3);
\end{circuitikz}
\end{document}
```

