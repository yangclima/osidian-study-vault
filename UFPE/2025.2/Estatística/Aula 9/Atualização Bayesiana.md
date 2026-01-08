Utilizando a [[Probabilidade Condicional]], definimos o conceito de **verossimilhança** ou **função verossimilhança** e a partir deles estabelecemos o método das [[Estimativas de máxima verossimilhança]], que nos permite aproximar o valor dos parâmetros de uma distribuição a partir do dados obtidos de um experimento, além disso, vimos brevemente que o [[Teorema de Bayes]] é a base da estatística inferencial já que utilizando-o podemos avaliar a probabilidade de uma hipótese qualquer baseando-se num conjunto de dados, é chegada então a hora de voltarmos nossos olhos novamente para este teorema e encontrarmos uma nova forma de utilizá-lo para calcular o que chamamos de **probabilidade à posteriori** utilizando o conceito de **verossimilhança** e o um conceito novo, denominado **probabilidade a priori**.

Introduziremos esses novos conceitos a partir de um exemplo ilustrativo, além disso, atente-se a terminologia utilizada.

Numa gaveta, há $5$ moedas, $2$ do tipo $A$, caracterizadas por uma probabilidade de $0.5$ de obter *cara*, $2$ do tipo $B$ cuja probabilidade de obter *cara* é $0.6$ e $1$ do tipo $C$ para a qual a probabilidade de obter *cara* é $0.9$.

- **Experimento:** Escolhemos aleatoriamente uma moeda na gaveta, realizamos o seu lançamento e guardamos o resultado.
- **Dados ($\mathcal{D}$):** Nossos dados são o resultado do experimento, nesse caso, obtivemos *cara*.
- **Hipótese ($\mathcal H$):** As hipóteses são os eventos dos quais queremos avaliar a probabilidade, ou, interpretando de outra forma, nosso chutes baseados no resultado do experimento, nesse caso as hipóteses são: A moeda é do tipo $A$, do tipo $B$ ou do tipo $C$ (Denotaremos essas hipóteses por $A$, $B$ e $C$ respectivamente).
- **Probabilidade a priori:** A probabilidade a priori é a probabilidade das nossas hipóteses antes da realização do experimento, nesse caso, dada a quantidade de cada tipo de moeda $P(A) = P(B) = 0.4$ e $P(C) = 0.2$.
- **Verossimilhança:** A verossimilhança, como já vimos, é a compatibilidade dos nosso dados com cada hipótese, ou a sua probabilidade assumindo as hipóteses como verdadeiras, nesse caso, temos $P(\mathcal{D}|A) = 0.5$, $P(\mathcal{D}|B) = 0.6$ e $P(\mathcal{D}|C) = 0.9$.
- **Probabilidade a posteriori:** A probabilidade a posteriori é a probabilidade de cada hipótese após a realização do experimento, ou seja, já considerando o seu resultado, nesse caso, é essa probabilidade que queremos obter, ou seja, $P(A|\mathcal{D})$, $P(B|\mathcal{D})$ e $P(C|\mathcal{D})$.

Para obter esses valores, no caso, a Probabilidade à posteriori das nossa hipóteses, utilizaremos um processo chamado de **Atualização Bayesiana** que fica mais simples utilizando uma **tabela de atualização Bayesiana**, a ideia é basicamente utilizar o [[Teorema de Bayes]] para encontrar os valores que queremos:

|   Hipótese    |      Priori      |        Verrossimilhança        |              Numerador de Bayes              |           Posteriori           |
| :-----------: | :--------------: | :----------------------------: | :------------------------------------------: | :----------------------------: |
| $\mathcal{H}$ | $P(\mathcal{H})$ | $P(\mathcal{D}\| \mathcal{H})$ | $P(\mathcal{D}\| \mathcal{H})P(\mathcal{H})$ | $P(\mathcal{H}\| \mathcal{D})$ |
|      $A$      |      $0.4$       |             $0.5$              |                    $0.2$                     |            $0.3226$            |
|      $B$      |      $0.4$       |             $0.6$              |                    $0.24$                    |            $0.3871$            |
|      $C$      |      $0.2$       |             $0.9$              |                    $0.18$                    |            $0.2903$            |
|   **Total**   |       $1$        |               -                |            $P(\mathcal D) = 0.62$            |              $1$               |

Perceba que o total da soma dos valores da coluna do **Numerador de Bayes** é igual a probabilidade dos dados, pelo [[Lei da Probabilidade Total]] e que os valores da última coluna foram calculados pelo [[Teorema de Bayes]], ou seja, utilizando:

$$
P(\mathcal{H}| \mathcal{D}) = \dfrac{P(\mathcal{D}| \mathcal{H})P(\mathcal{H})}{P(\mathcal{D})}
$$

Verificando então a tabela, vemos que dado o nosso experimento,  a hipótese mais provável é que a moeda seja do tipo $B$.

Perceba também que como todos os valores da coluna do Numerador de Bayes estão sendo divididos pelo mesmo valor para obter a probabilidade a priori, o fator $P(\mathcal D)$ funciona apenas para normalizar a probabilidade a posteriori total para $01$ e apenas olhando para o numerador de Bayes já seria possível identificar que a hipótese mais provável era a $B$, assim, é útil expressar o teorema de Bayes como:

$$
P(\mathcal{H}| \mathcal{D}) \propto P(\mathcal{D}| \mathcal{H})P(\mathcal{H})
$$

Chegando assim numa forma mais elegante do teorema de Bayes que relaciona os novos termos que introduzimos:

$$
\text{Posteriori}\propto \text{Verossimilhança}\cdot \text{Priori}
$$

É daí que vem o termo **atualização Bayesiana**, basicamente atualizamos uma probabilidade anterior ao experimento para uma probabilidade posterior ao experimento.

Além disso é possível repetir indefinidamente o atualização Bayesiana, digamos por exemplo que lançamos novamente a moeda que selecionamos ao acaso e obtivemos novamente cara, assim, teríamos:

|   Hipótese    |      Priori      |       Verossimilhança 01       |            Numerador de Bayes 01             |       Verossimilhança 02       |                          Numerador de Bayes 02                           |           Posteriori           |
| :-----------: | :--------------: | :----------------------------: | :------------------------------------------: | :----------------------------: | :----------------------------------------------------------------------: | :----------------------------: |
| $\mathcal{H}$ | $P(\mathcal{H})$ | $P(\mathcal{D}\| \mathcal{H})$ | $P(\mathcal{D}\| \mathcal{H})P(\mathcal{H})$ | $P(\mathcal{D}\| \mathcal{H})$ | $P(\mathcal{D}\| \mathcal{H})P(\mathcal{D}\| \mathcal{H})P(\mathcal{H})$ | $P(\mathcal{H}\| \mathcal{D})$ |
|      $A$      |      $0.4$       |             $0.5$              |                    $0.2$                     |             $0.5$              |                                  $0.1$                                   |            $0.2463$            |
|      $B$      |      $0.4$       |             $0.6$              |                    $0.24$                    |             $0.6$              |                                 $0.144$                                  |            $0.3546$            |
|      $C$      |      $0.2$       |             $0.9$              |                    $0.18$                    |             $0.9$              |                                 $0.162$                                  |            $0.3990$            |
|   **Total**   |       $1$        |               -                |            $P(\mathcal D) = 0.62$            |               -                |                         $P(\mathcal D) = 0.406$                          |              $1$               |

Assim, percebemos que obtendo a segunda cara, a hipótese $C$ se torna então a mais provável.