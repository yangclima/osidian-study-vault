---
next: "[[Lei de Kirchhoff das Tensões]]"
prev: "[[Terminologia]]"
---
A primeira definição essencial que nos permitirá desenvolver nosso método de análise de circuitos é a chamada **Lei de Kirchhoff das Correntes** ou **Lei dos Nós**, por simplicidade, iremos nos referir a essa lei como **LKC**, que se aplica aos [[Terminologia|nós do circuito]] e define o seguinte:

----

**LKC:** A [[Corrente]] saindo de qualquer nó do circuito deve ser igual a corrente entrando nele, de forma análoga, a soma algébrica das [[Terminologia|correntes de ramo]] que fluem para qualquer nó, deve ser $0$, isto é, considerando coerentemente o sinal das correntes.

$$
\sum_{n=1}^N i_n = 0
$$

----

De maneira intuitiva, a LKC é uma consequência da conservação de [[carga]], dado que na nossa [[Abstração de Circuitos]] consideramos como premissa básica que a carga não se acumula ao longo do circuito.

Uma conclusão importante obtida através da análise de circuitos formados por componentes em série como o seguinte:


```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}

\draw[scale=2]
(0,0) to[generic, i=$i_1$, o-o] 
(2,0) to[generic, i=$i_2$, o-o] (4,0);


\end{circuitikz}
\end{document}
```

Onde a análise nodal permite inferir que **a corrente de ramo passando ao longo de múltiplos elementos em série deve ser sempre a mesma**, não importando o número de componentes.

Quanto a matemática, analisando um circuito com $N$ nós e obtendo a equação proveniente da LKC para cada um deles, cada corrente deve surgir duas vezes nas equações, uma vez positiva e outra negativa o que permite identificar rapidamente erros na construção das equações, outro fato é que, uma das $N$ equações obtidas vai ser linearmente dependente das outras, isto é, é necessário e suficiente analisar apenas $N-1$ nós para abstrair todas as informações possíveis com a LKC.