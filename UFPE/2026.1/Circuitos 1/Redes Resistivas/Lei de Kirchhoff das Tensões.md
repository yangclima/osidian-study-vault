---
next: "[[Método Básico de Análise de Circuitos]]"
prev: "[[Lei de Kirchhoff das Correntes]]"
---
Além da [[Lei de Kirchhoff das Correntes]], a segunda relação algébrica que nos permitirá realizar a análise dos circuitos é a chamada **Lei de Kirchhoff das Tensões** ou **Lei da Malhas** a qual iremos nos referir como **LKT**, por simplicidade, que se aplica aos [[Terminologia|laços]] do circuito e define que:

----

**LKT:** A soma algébrica das tensões de ramo em qualquer caminho fechado em um circuito deve ser sempre $0$.

$$
\sum_{n=1}^N v_n = 0
$$

----

De forma alternativa, a LKT define que a [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|diferença de potencial]] entre dois nós é independente do caminho ao longo do qual esta diferença é acumulada.

É importante ter em mente que dada a nossa [[Convenção de Variáveis Associadas]], as tensões tem sinais positivos quando atravessamos os componentes indo do terminal positivo para o negativo e sinais negativos caso contrário, um bom mnemônico para lidar com isso é atribuir a cada tensão o sinal do terminal que você primeiro encontrar ao atravessar um componente.

Dada a definição de potencial elétrico, a LKT é simplesmente uma definição da conservação de energia, dado que, pela nossa [[Abstração de Circuitos]], assumimos que o [[Fluxo magnético]] ao longo de qualquer caminho fechado do circuito é $0$, além disso, podemos interpretar essa lei como consequência do pressuposto de que a tensão em cada nó está univocamente definida.

Uma conclusão importante da LKT é que em circuitos formados por componentes em paralelo como o seguinte:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}
\draw[american, scale=1.5]
(0,0) -- 
(2,0) --
(2,1) to[generic, v=$v_1$] 
(4,1) -- (4,0) -- (6,0) -- (4,0) --
(4,-1) to[generic, v=$v_2$]
(2,-1) --
(2,0);
 
\end{circuitikz}
\end{document}
```

Podemos obter através dessa lei que a tensão entre múltiplos elementos conectados em paralelo deve ser sempre a mesma.

Em geral, se um circuito possui $N$ nós e $R$ ramos, então há $B - N + 1$ laços através dos quais podemos obter equações independentes, o que equivale a $L$ laços que resultarão em $L$ equações LKC, onde, notoriamente cada tensão deve aparecer uma vez positiva e outra negativa (Isso permite identificar erros na construção das equações facilmente), das quais, $L-1$ das equações serão independentes.