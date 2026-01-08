Circuitos digitais de [[Contador Síncrono|contadores síncronos]] podem ser projetados para gerar qualquer sequência de contagem desejada utilizando apenas as sua entradas de controle síncronas, isto é, sem utilizar a suas [[Entradas assíncronas]], o que é extremamente útil pela alta previsibilidade que isso confere a esses sistemas, evitando glitches e estados instáveis.

Primeiramente, precisamos ser capazes de analisar, dada a configuração do nosso circuito, que sequência de contagem é gerada por ele, o que pode ser feita utilizando-se de uma **tabela de estado ATUAL/PRÓXIMO estado**, por exemplo:

![[sd_038.png|center]]


A ideia é analisar o circuito partindo do estado nulo, avaliar as [[Álgebra Booleana|expressões booleanas]] para cada uma das entradas de controle (obtidas através da análise do circuito) e utilizando esses valores e com base nelas avaliar o próximo estado de cada um dos [[Flip-flop J-K com clock|flip-flops]] e portanto o próximo estado do contador, depois disso, utilizamos esse novo estado como estado atual, reavaliamos as estradas de controle e seu efeito no estados dos FF's e repetimos o processo para encontrar os próximos estados para cada um dos estados atuais possíveis do contador.

Uma outra tabela que pode ser útil é a seguinte, que demonstra o funcionamento do flip-flop J-K:

| $J$ | $K$ | $Q_0$ | $Q_1$ |
| --- | --- | ----- | ----- |
| $0$ | $X$ | $0$   | $0$   |
| $1$ | $X$ | $0$   | $1$   |
| $X$ | $0$ | $1$   | $1$   |
| $X$ | $1$ | $1$   | $0$   |

Onde $J$ e $K$ são as entradas síncronas de controle, $Q_0$ é o estado atual do flip-flop, $Q_1$ é o próximo estado do flip-flop e $X$ é o sinal equivalente a *don't care*.

Um outro conceito importante nesse contexto é o de **contador autocorretor** a ideia aqui é simples, um contador deve ter um ciclo de estados fechado e aquele que é capaz de voltar para esse ciclo mesmo que partindo de um estado que não pertença a esse ciclo é denominado de **contador autocorretor**.