---
next: "[[Divisores de Tensão e Corrente]]"
prev: "[[Lei de Kirchhoff das Tensões]]"
---
Agora que conhecemos a [[Lei de Kirchhoff das Tensões]] e a [[Lei de Kirchhoff das Correntes]] podemos desenvolver o nosso primeiro método de análise de circuitos, a ideia é simples, queremos montar as equações provenientes da LKC, LKT e das [[Lei de Elemento|Leis de Elemento]] e então resolver um [[Sistemas lineares|Sistema Linear]] para encontrar as nossas variáveis de circuito, isto é, a [[Potencial elétrico|tensão]] e a [[Corrente]] ao longo de cada elemento do nosso circuito. Seguimos então os seguintes passos:

1. Defina arbitrariamente a polaridade de cada elemento no seu circuito, rotulando cada elemento com uma tensão de ramo e de maneira consistente com a [[Convenção de Variáveis Associadas]], defina as correntes de ramo de cada elemento.
2. Escreva a Lei de Elemento para cada um dos Elementos no seu circuito.
3. Escreva as equações provenientes de LKC e LKT, isto é, as relações entre as correntes e tensões no seu circuito.
4. Resolva o sistema linear

Vamos ilustrar o processo com o seguinte exemplo de circuito:

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


Primeiro (01), rotulamos arbitrariamente as tensões e correntes no nosso sistema seguindo a [[Convenção de Variáveis Associadas]]:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american]

\draw
(0,3) to[vsource, v=$v_0$, i>=$i_0$] 
(0,0) to[R=$R_1$, v=$v_1$, i=$i_1$] (3,0)
to[R=$R_2$, i=$i_2$, v=$v_2$, i=$i_2$] (3,3) -- (0,3);

\draw
(3,0) -- 
(6,0) to[R=$R_3$, v=$v_3$, i=$i_3$] 
(6,3) -- (3,3);

\end{circuitikz}
\end{document}
```

Agora (02), reunimos as nossas leis de elemento:

$$
\begin{cases}
v_0 = V \\
v_1 = i_1R_1 \\
v_2 = i_2R_2 \\
v_3 = i_3R_3 \\
\end{cases}
$$

O terceiro passo (03) é aplicar LKC e LKT:

$$
\begin{cases}
v_0 + v_1 + v_2 = 0 \\
-v_2 + v_3 = 0
\end{cases}
$$
$$
\begin{cases}
i_0 - i_1 = 0 \\
i_1 - i_2 - i_3 = 0
\end{cases}
$$

Por fim (04), mesclando as equações encontradas, encontramos o seguinte sistema linear:

$$
\begin{cases}
V + i_1R_1 + i_2R_2 & = 0 \\
\ \ \ \ \ \ \ \ i_1R_3 + i_2(-R_2 - R_3) & = 0
\end{cases}
$$

Que pode ser escrito como a seguinte relação de [[Matrizes]]:

$$
\begin{bmatrix}
R_1 & R_2 \\
R_3 & -R_2-R_3
\end{bmatrix}
\begin{bmatrix}
i_1 \\
i_2
\end{bmatrix} =
\begin{bmatrix}
-V \\
0
\end{bmatrix}
$$

Então, podemos utilizar a regra de Cramer, encontrando:

$$
i_1 = i_0 = \dfrac{V(R_2+R_3)}{-R_1R_2 - R_1R_3 -R_2R_3}
$$
$$
i_2 = \dfrac{VR_3}{-R_1R_2 - R_1R_3 -R_2R_3}
$$
$$
i_3 = \dfrac{VR_2}{-R_1R_2 - R_1R_3 -R_2R_3}
$$


E as tensões de ramo podem ser encontradas multiplicando essas correntes pelas [[Resistência|resistências]].

Em resumo, esse é um processo que pode ser utilizado para resolver qualquer rede resistiva.

$$

$$

