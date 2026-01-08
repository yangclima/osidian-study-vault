Os sistemas digitais podem operar de dois modos, no modo *assíncrono*, onde as saídas dos circuitos podem mudar a qualquer momento, e no modo *síncrono*, onde os momentos onde essas saídas podem mudar são sincronizados por um sinal denominado **clock**.

O clock é um trem de [[Pulsos Digitais]] ou uma onda quadrada e costuma ser distribuído para todas as partes do sistema, padronizando o momento de mudança das diferentes partes do circuito a partir dos momentos de transição do clock, ou seja, as saídas só mudam nos momentos em que há uma transição do clock para o nível positivo (Borda de subida) ou uma transição para o nível negativo (Borda de descida).

A sincronização dos eventos com o clock é obtida usando [[Memória|flip-flops]] com clock, projetados para mudar de estado em uma das transições do sinal de clock.

Nesse caso, a velocidade dos sistemas digitais é determinada pela frequência em que ocorrem os ciclos de clock. O tempo para completar um ciclo, ou seja, o tempo entre duas bordas de clock é denominado **Período** ($T$) e a quantidade desses ciclos que acontecem em um segundo e portanto o que determina a velocidade do sistema digital é a **frequência** ($f$), cuja unidade padrão é o $Hz$ que equivale a $1$ ciclo por segundo.

As principais propriedades dos flip-flops com clock, são:

1. Tem uma **entrada de clock**, normalmente designada por *CLK*, *CK* ou *CP* (clock pulse), normalmente essa entrada é disparada por borda, ou seja é ativa pela transição do sinal de clock, oque costuma ser indicado por uma pequeno triângulo nessa entrada, e indica uma ativação por borda de subida ou um pequeno triângulo com uma bolinha, que costuma designar uma ativação por borda de descida.
2. Possuem uma ou mais **entradas de controle**, essas entradas, a depender do funcionamento do respectivo flip-flop terão diferentes efeitos sob a saída do flip-flop, mas esse efeito só será mensurado em sincronia com o pulso de clock, por isso são chamadas de **entradas de controle síncronas**, assim, podemos dizer que as entradas de controle deixam as saídas do flip-flop prontas para mudar de estado, mas essa mudança é disparada apenas pelo clock.
3. Os flip-flops tem dois tempos característicos, o **tempo de setup** $t_S$, tempo no qual as entradas de controle devem ser mantidas no nível adequado e precede a transição ativa do sinal de clock e o **tempo de hold** $t_H$, tempo o qual se segue imediatamente depois da transição ativa do clock no qual as entradas de controle devem ser mantidas no nível adequado, assim, para garantir que um FF com clock responda adequadamente quando ocorrer a transição ativa, as entradas de controle têm de estar estáveis (imutáveis) por pelo menos um intervalo de tempo igual a $t_S(mín)$ antes da transição do clock e por pelo menos um intervalo de tempo igual a $t_H(mín)$ após a transição do clock.



