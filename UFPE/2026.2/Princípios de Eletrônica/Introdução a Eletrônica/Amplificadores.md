Conceitualmente, uma das funções mais importantes do processamento de [[Sinais|sinais]] é a **Amplificação de sinal**, isso por que os [[Dispositivos de medição|transdutores]] geram sinais fracos, de baixas amplitudes e baixa energia e se tornam muito mais simples de processar caso sua amplitude fosse maior, aumentar a amplitude é então a operação realizada pelo bloco fundamental chamado de **Amplificador de sinal**.

É obviamente muito importante que o amplificador seja capaz de aumentar a amplitude do sinal mas sem distorce-lo, modificá-lo, assim evitando a perda de informação, lembre-se que a informação de um sinal está contida na forma específica que ele varia e oscila no tempo, por isso, precisamos que exista uma **linearidade** nos amplificadores, de modo que o sinal $v_o$ que sai de um amplificador se relaciona com o sinal de entrada $v_i$ do mesmo conforme a relação a seguir:

$$
v_o(t) = Av_i(t)
$$

Onde $A$ é uma constante que representa o fator de amplificação e é conhecido com **Ganho do amplificador** e dada a linearidade dessa relação, chamamos os amplificadores que seguem essa relação de **amplificadores lineares**. Esses amplificadores em geral são utilizados para aumentar a amplitude de sinais fracos sendo chamados de **amplificadores de tensão**.

Um outro tipo de amplificador é o **amplificador de potência**, que fornece um ganho pequeno na tensão, porém, um ganho substancial na corrente, aumentando a **potência** do sinal.

Obviamente, um amplificador é um dispositivo de 4 terminais (Quadripolo), de forma geral sendo representado pela parte $(a)$ da seguinte imagem com dois terminais distintos para a entrada e dois para a saída, entretanto, o caso mais comum é representado na parte $(b)$ com um dos terminais sendo comum e usado como referência e chamado de **terra do circuito**.

![[pe_008.png|1000]]

Consideremos agora o seguinte circuito:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{tikzpicture}[american, scale=1.2]
    % Fonte de tensão de entrada (senoidal)
    \draw (0, 1.5) to[sV, l=$v_I(t)$] (0, 0);

    % Linhas de entrada com terminais e indicação de corrente
    \draw (0, 1.5) to[short, -o] (0.8, 1.5)
          to[short, o-, i=$i_I$] (1.8, 1.5);
    \draw (0, 0) to[short, -o] (0.8, 0)
          to[short, o-] (2.2, 0);

    % Buffer / Amplificador
    \draw (1.8, 1.5) node[buffer, anchor=in] (amp) {};

    % Linha comum inferior e aterramento
    \draw (amp.south) ++(0,0.27) -- (amp.south |- 0,0) node[circ]{} 
          to[short] ++(0, -0.25) node[ground]{};

    % Linhas de saída com terminais e indicação de corrente
    \draw (amp.out) to[short, -o] (3.6, 1.5)
          to[short, o-, i=$i_L$] (4.6, 1.5);
    \draw (2.2, 0) to[short, -o] (3.6, 0)
          to[short, o-] (4.6, 0);

    % Resistor de carga RL e tensão de saída
    \draw (4.6, 1.5) to[R, l_=$R$, v^=$v_O(t)$] (4.6, 0);
\end{tikzpicture}
\end{document}
```

Analisando esse circuito temos então um ganho dado por:

$$A_v = \frac{v_O}{v_I}$$

Isso significa nada mais do que "Se aplicarmos na entrada uma tensão $\hat V$ obteremos na saída uma tensão $A\hat V$", podemos inclusive  mostrar essa amplificação num gráfico $v_I\times v_O$ e nesse caso $A$ será representada pelo coeficiente angular da reta formada escrevendo $v_O$ em função de $v_I$, chamada de **característica de de transferência** do amplificador.

Uma distinção interessante aparece aqui, o amplificador, diferente dos [[Transformadores]] pode aumentar a [[Potência]] do sinal, ao contrário do trafo que fornece uma potência no secundário menor ou igual a potência no primário, por isso, teremos um **ganho de potência** $A_p$ associado ao amplificador que não é tão direto, afinal, o **ganho de corrente** dado por

$$A_i = \frac{i_O}{i_I} = \frac{v_O}{Ri_I}$$

Onde $i_I$ é a corrente que o amplificador drena da fonte do sinal, assim, nosso ganho de potência é:

$$A_p = \frac{p_O}{p_I}= \frac{v_Oi_O}{v_Ii_I} \implies A_p = A_iA_v$$

Esses ganhos, na verdade, por razões históricas são, por vezes, representados em decibéis, em parte por que os valores desses ganhos podem ser negativos simplesmente por conta da fase que o sinal de saída assume com o de entrada (Fase de $180\degree$), porém isso não significa que atua o sinal, por outro lado, um ganho negativo em decibéis significa de fato que o amplificador atenua esse sinal de entrada, assim temos:

$$\text{Ganho de tensão em decibéis} = 20\log|A_v|$$
$$\text{Ganho de corrente em decibéis} = 20\log|A_i|$$
$$\text{Ganho de potência em decibéis} = 10\log|A_v|$$

Percebendo então que o amplificador é capaz de amplificar a potência, o [[teorema de Tellegen]] nos força  a buscar a fonte dessa potência no sistema, o fato é que os amplificadores precisam ser alimentados por fontes de [[Potencial elétrico|tensão]] [[Corrente|CC]] que fornecem essa potência adicional bem como a potência que acabará internamente dissipada no circuito do amplificador.

Os amplificadores mais comuns são alimentados por duas fontes de tensão cc em dois terminais extras rotulados $V^+$ e $V^-$ de modo que para operar o terminal $V^+$ deve ser conectado ao terminal positivo de uma fonte de tensão $V_1$ (Fonte cujo terminal negativo será conectado ao terra do circuito) e o terminal $V^-$ deve ser conectado ao negativo uma fonte de tensão $V_2$ que deve ter seu positivo conectado ao terra do circuito e teremos então uma potência entregue ao amplificador dada por:

$$P_{cc} = V_1I_1 + V_2I_2$$

Então, denotando a potência dissipada no amplificador por $P_{dis}$ teremos o seu balanço de potência descrito por:

$$P_{cc} + P_I = P_L + P_{dis}$$

Onde $P_I$ é a potência drenada da fonte do sinal e $P_L$ a fonte fornecida a carga, como $P_I$ é normalmente muito pequena temos a eficiência do amplificador dada por:

$$\eta = \frac{P_L}{P_{cc}}\times 100$$

De forma simplificada denotaremos então o amplificador usando:


```tikz
\usepackage[european, straightvoltages, RPvoltages, americanresistor, americaninductors]{circuitikz}

\begin{document}
\begin{tikzpicture}[line width=0.2mm]
    \ctikzset{bipoles/thickness=1.2}

    % Amplificador Operacional no centro
    \draw (0,0) node[op amp] (opamp) {};
    
    % Entradas e Saída com caminhos relativos nativos
    \draw (opamp.+) -- ++(-0.8,0) node[left] {$v_+$};
    \draw (opamp.-) -- ++(-0.8,0) node[left] {$v_-$};
    \draw (opamp.out) to[short,-*] ++(0.8,0) node[right] {$v_\mathrm{O}$};
    
    % Alimentação (usando setas padrão -latex)
    \draw[-latex] (opamp.up) -- ++(0,1) node[above] {$V_+$};
    \draw[-latex] (opamp.down) -- ++(0,-1) node[below] {$V_-$};
    
    % Diferença de potencial (vd) - Desenhada com coordenadas absolutas para evitar a biblioteca 'calc'
    \draw[-latex] (-1.5, 0.4) -- (-1.5, -0.4) node[midway, left] {$v_\mathrm{d}$};

\end{tikzpicture}
\end{document}
```

