Um [[Transformadores|transformador]] é um dispositivo que faz uso do fenômeno da [[Indução mútua]] para realizar transformações de [[Potencial elétrico|tensão]] e [[Corrente|corrente]], nesse sentido, um transformador (Ou trafo) é um dispositivo de 4 terminais formado por duas ou mais bobinas [[Acoplamento magnético|magneticamente acopladas]].

A bobina conectada a fonte é chamada de **enrolamento primário**, enquanto a a [[Indutores|bobina]] ligada a carga é denominada **enrolamento secundário** e temos, além disso, [[Resistores Lineares|resistências]] incorporadas no modelo para levar em conta as perdas do dispositivo.

```tikz
\usepackage{circuitikz}

\begin{document}

\begin{circuitikz}[american]

    % --- Malha Primária (Esquerda) ---
    \draw (0,0) to[V, invert, l=$\mathbf{V}$] (0,3)
          to[R, l=$R_1$] (3,3)
          to[L, l_=$L_1$, name=L1] (3,0)
          -- (0,0);

    % --- Malha Secundária (Direita) ---
    \draw (4.5,3) to[L, l=$L_2$, name=L2] (4.5,0)
          -- (7.5,0)
          to[generic, l_=$\mathbf{Z}_L$, fill=gray!20] (7.5,3)
          to[R, l_=$R_2$] (4.5,3);

    % --- Pontos de Polaridade (Acoplamento) ---
    % Adiciona as bolinhas pretas indicando a polaridade
    \node[circle, fill, inner sep=1.2pt] at (2.65, 2.3) {};
    \node[circle, fill, inner sep=1.2pt] at (4.85, 2.3) {};

    % --- Indutância Mútua (Arco com Setas Duplas M) ---
    \draw[<->, >=latex] (3.2, 3.2) to[bend left=45] node[above] {$M$} (4.3, 3.2);

    % --- Correntes de Malha ---
    % Arco da Corrente I1
    \draw[-latex] (1.04, 1.88) arc[start angle=140, end angle=-140, radius=0.6];
    \node at (1.5, 1.5) {$\mathbf{I}_1$};

    % Arco da Corrente I2
    \draw[-latex] (5.54, 1.88) arc[start angle=140, end angle=-140, radius=0.6];
    \node at (6.0, 1.5) {$\mathbf{I}_2$};

\end{circuitikz}

\end{document}
```

Chamamos um transformador de **Transformados linear** caso as bobinas sejam enroladas em um material [[Magnetização em Materiais|magneticamente linear]], como ar, plástico ou a maioria dos materiais. 

Analisando matematicamente, podemos encontrar a **impedância de entrada** vista pela fonte como sendo dada por:

$$\hat Z_{ent} = R_1 + j\omega L_1 + \frac{\omega^2M^2}{R_2 + j\omega L_2 + Z_L}$$


Note que $R_1 + j\omega L_1$ é a impedância própria da malha 1, do primário, sendo assim, é normalmente chamada de **impedância primária**, impedância do primário ou autoimpedância, a fração na expressão acima, por outro lado, se deve ao acoplamento com o secundário, sendo assim chamada de 
autoimpedância do secundário ou mais comumente de **Impedância refletida ao primário** $\hat Z_R$, dada por:

$$\hat Z_R = \frac{\omega ^2 M^2}{R_2 + j\omega L_2 + Z_L}$$

Note também que $R_2 +j\omega L_2+Z_L$ é a impedância total do secundário $\hat Z_{22}$. Nesse contexto, chamamos de fator de escala a razão entre a impedância refletida e a impedância do secundário:

$$\text{Fator de escala} = \frac{|\hat Z_r|}{|\hat Z_{22}|}$$

Apesar de até agora termos lidado com circuitos magnéticos aplicando [[Análise de malha]], é possível resolver esse circuitos simplesmente por inspeção, tal qual fazíamos com restrições para a análise de malha em circuitos com apenas fontes de tensão ou [[Análise Nodal]] de circuitos apenas com fontes de corrente.

Quando tivermos apenas fontes de tensão independentes no circuito e estivermos considerando apenas o regime permanente senoidal, sem fontes controladas e adotando um sentido padrão de circulação nas malhas, podemos montar um sistema de [[Matrizes]] forma $[Z] [I] = [V]$, para isso, seguimos:

1. Primeiro, expressamos todo o circuito no domínio da frequência e definimos as correntes de malha e seus sentidos (Por convenção, horário)
2. Para preencher a diagonal da matriz $[Z]$, isto é, os elementos $\hat Z_{ii}$, tomamos a soma de todas as [[Impedância e Admitância|impedâncias]] na malha $i$, se a malha contiver duas [[Indutores em Circuitos|bobinas]] acopladas entre si, some à [[Impedância|impedância]] da malha $2\hat Z_m$ se a corrente da malha entrar ou sair pelo ponto em ambas e subtraia esse valor caso contrário.
3. Para preencher os valores $\hat Z_{ij}$ comece somando o negativo das impedâncias compartilhadas entre as malhas $i$ e $j$, caso haja acoplamento magnético entre bobinas da malha $i$ e da malha $j$, some $\hat Z_m$ caso ambas as correntes nas bobinas entrem ou ambas saiam pelo terminal com o ponto e subtraindo o mesmo valor caso o contrário.
4. Agora, preenchemos os valores de $[V]$ com as fontes de tensão presentes em cada malha tomando seu valor positivo caso a corrente da respectiva malha entre pelo terminal negativo da fonte e caso contrário, adote seu valor positivo

Por fim, uma interessante possibilidade é transformar um circuito de um transformador linear em um circuito sem acoplamento magnético usando seu equivalente delta ou estrela, dado da seguinte maneira:

![[circ2_003.png]]

Onde temos:

$$L_1 = \mathbb{L_1} - M; \ \ \ \ L_2 = \mathbb{L_2} -M \ \ \ \ \text{e} \ \ \ \ L_3 = M$$

Ou para ao seu equivalente Delta:

![[circ2_004.png]]

Onde:

$$L_a = \frac{L_1L_2 - M^2}{L_2-M}; \ \ \ \ L_b = \frac{L_1L_2 - M^2}{L_1 -M} \ \ \ \ \text{e} \ \ \ \ L_3 = \frac{L_1L_2 - M^2}{M}$$

