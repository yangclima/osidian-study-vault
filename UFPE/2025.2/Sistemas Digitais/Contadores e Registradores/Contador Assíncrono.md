Agora que já sabemos como funcionam os circuitos sequenciais, podemos combinar esses dispositivos que possuem [[Memória]] em circuitos mais complexos, dentre os quais se destacam os **contadores** e os **registradores**.

O primeiro desses circuitos que veremos é o **Contador Assíncrono**, assim chamado por que o estado de cada um dos [[Flip-flop J-K com clock|Flip-flops]] muda de maneira assíncrona, isto é, não sincronizada entre si.

A ideia é utilizar  [[Flip-flop J-K com clock|Flip-flops J-K]] conectados em série com a saída de cada flip-flop conectada no clock do flip-flop seguinte e com as entradas $J$ e $K$ sempre ativas, assim, sempre que houver uma borda de descida $CLK$ do primeiro ff da série o seu valor será atualizado, gerando, a cada dois pulsos de [[Sinais de Clock e Flip-Flops com clock|clock]] um pulso completo no $CLK$ do ff seguinte. A cada flip-flop, ocorre então uma divisão de frequência e é assim que se constrói a contagem binária sequencial do flip flop.

A montagem do circuito está exibida abaixo:

![[sd_030.png]]

Perceba que ao contrário da forma com que costumamos representar os circuitos, da esquerda para a direita, representamos esse em específico na direção contrária, isso deve-se ao fato de que, utilizando essa configuração, a saída do flip-flop mais a direita, corresponde ao bit menos significativo, e a saída do flip-flop mais a esquerda corresponde ao bit mais significante, ou seja, de maneira compatível com a forma na qual representamos os números binários.

Note também que os clocks dos ff's são do tipo **borda de descida**, trocando isso para o tipo borda de subida, obtemos então um contador assíncrono decrescente.

Um outro conceito importante é o **módulo** do contador que corresponde ao número de estados possíveis nesse circuito, no nosso caso, da forma que estamos trabalhando, o módulo é dado por:

$$
MOD = 2^N
$$

Onde $N$ é o número de flip-flops.

O grande problema dos contadores assíncronos é que o atraso de propagação de cada flip-flop se acumula ao longo do circuito o que é extremamente relevante em altas frequências, o problema é que se o período do clock for menor que o atraso acumulado ao longo do circuito as ondas ficarão distorcidas e os valores ficarão distorcidos ao longo da contagem, nesse caso, vale que, o valor máximo para a frequência do clock é:

$$
f_{max} = \dfrac{1}{N\cdot t_{pd}}
$$

Onde $N$ é o número de flip-flops e $t_{pd}$ o tempo de atraso de cada flip-flop.


