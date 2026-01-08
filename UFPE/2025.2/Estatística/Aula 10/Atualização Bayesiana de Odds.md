Assim como definimos a [[Atualização Bayesiana]] para a [[Função probabilidade|probabilidade]] de um evento, podemos fazer o mesmo para as [[Odds|Odds]], ou seja, atualizar um **Odd a priori** para uma **Odd a posteriori** utilizando o [[Teorema de Bayes]].

Considere uma determinada doença a qual $0.5\%$ da população apresenta e cujo o teste clínico para diagnóstico resulta em $99\%$ de verdadeiros positivos e $2\%$ de falsos positivos. 

Primeiro, queremos saber qual a Odd de uma pessoa escolhida aleatoriamente ter a doença, nesse caso $D$ é a probabilidade da pessoa ter a doença e $D^c$ é a probabilidade dela não ter, assim:

$$
O(D) = \dfrac{P(D)}{P(D^c)} = \dfrac{0.005}{0.995} \approx 0.005
$$

Essa é a **Odd a priori** da pessoa ter a doença,  agora, digamos que essa pessoa escolhida aleatoriamente, testou positivo para a doença ($T$), queremos então utilizar a atualização Bayesiana para avaliar a **Odd a posteriori** dessa pessoa de fato ter a doença ($D$), temos então:

$$
O(D|T) = \dfrac{P(D|T)}{P(D^c|T)} = \dfrac{P(T|D)P(D)/\cancel{P(T)}}{P(T|D^c)P(D^c)/\cancel{P(T)}} = \dfrac{P(T|D)P(D)}{P(T|D^c)P(D^c)}
$$

Podemos utilizar então uma tabela de atualização Bayesiana para obter esses valores o que resultará em:

$$
O(D|T) = \dfrac{0.99\cdot0.005}{0.02\cdot0.995} \approx 0.25 = \dfrac{1}{4}
$$

Se organizássemos isso em uma tabela teríamos:

|   Hipótese    |      Priori      |   Verossimilhança   |        Numerador de Bayes         |     Posteriori      |
| :-----------: | :--------------: | :-----------------: | :-------------------------------: | :-----------------: |
| $\mathcal{H}$ | $P(\mathcal{H})$ | $P(T\|\mathcal{H})$ | $P(\mathcal{H})P(T\|\mathcal{H})$ | $P(\mathcal{H}\|T)$ |
|      $D$      |     $0.005$      |       $0.99$        |             $0.00495$             |      $0.19920$      |
|     $D^c$     |     $0.995$      |       $0.02$        |             $0.01990$             |      $0.80080$      |
|   **total**   |       $1$        |          -          |         $P(T) = 0.02485$          |         $1$         |

Perceba que a Odd a priori é obtida pela razão dos termos da coluna da probabilidade a priori e a Odd a posteriori é obtida pela razão dos termos da coluna do Numerador de Bayes..

