Agora que conhecemos os [[Contador Síncrono|contares síncronos]] e também conhecemos uma procedimento para [[Análise de Contadores Síncronos|análise desses circuitos]], é chegada a hora de realizarmos projetos de contadores síncronos, isto é, desenvolvermos um método que permita aplicar [[Flip-flop J-K com clock|flip-flops J-K]] ou [[Flip-flop D com clock|flip-flops D]] para a criação de circuitos digitais sequenciais que seguem uma determinada ordem de estados estipulada no projeto.

A ideia é simples, para estes circuitos disparados por borda de [[Sinais de Clock e Flip-Flops com clock|clock]] precisamos garantir que a cada pulso de clock as entradas dos flip-flops estejam alimentadas por circuitos combinacionais de tal maneira que o próximo estado de cada flip-flop juntos formem o próximo estado desejado para o contador, esses  circuitos combinacionais, por sua vez, podem ser projetados utilizado as saídas dos flip-flops e projetados através de um [[Mapa de Karnaugh]].

O projeto de um contador síncrono pode então ser desmembrado nos seguintes passos:

1. Primeiro, determine o número de bits do contador e a sequência de estados desejada, organizando essa sequência em uma tabela.
2. Desenhe o diagrama de transição de estados desejado para o seu circuito de tal maneira que inclui nele os *estados indesejados* (Você também pode ignorar esses estados, mas isso pode gerar alguns problemas).
3. Crie uma **tabela de estado ATUAL/PRÓXIMO estado** com base nesse diagrama, isto é, preencha as colunas **estado atual** e **próximo estado** considerando o fluxo do seu contador determinado no diagrama
4. Adicione a coluna central com cada entrada dos flip-flops e considerando o comportamento destes, preencha os valores que devem estar em cada uma dessas entradas para sair de cada estado atual e chegar no próximo estado, lembre-se de considerar o *don't care* quando for possível.
5. Com base nos valores requeridos em cada entrada de controle, crie, para cada uma dessas entradas um [[Mapa de Karnaugh]] utilizando as saídas dos flip-flops como variáveis para encontrar a expressão na forma de soma de produtos para cada entrada de controle.
6. Por fim, implemente o circuito lógico planejado com base nas expressões obtidas.

Para o passo 4 é muito útil ter em mente a seguinte tabela, que ilustra o comportamento do flip-flops J-K:

| $J$ | $K$ | $Q_0$ | $Q_1$ |
| --- | --- | ----- | ----- |
| $0$ | $X$ | $0$   | $0$   |
| $1$ | $X$ | $0$   | $1$   |
| $X$ | $0$ | $1$   | $1$   |
| $X$ | $1$ | $1$   | $0$   |

Onde $J$ e $K$ são as entradas síncronas de controle, $Q_0$ é o estado atual do flip-flop, $Q_1$ é o próximo estado do flip-flop e $X$ é o sinal equivalente a *don't care*, utilizando essa mesma notação, a seguinte tabela, também muito útil, ilustra o comportamento dos flip-flops D:

| $D$ | $Q_0$ | $Q_1$ |
| --- | ----- | ----- |
| $0$ | $X$   | $0$   |
| $1$ | $X$   | $1$   |

