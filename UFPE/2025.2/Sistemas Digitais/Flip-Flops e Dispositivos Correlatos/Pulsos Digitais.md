Como vimos, num [[Latch com portas NOR]] ou num [[Latch com portas NAND]], a alteração do estado de [[Memória]] é feita através de um **pulso**, seja em nível ALTO, no caso do *latch NOR* ou em nível baixo, no caso do *Latch NAND*, **pulso** é a denominação dada para sinais digitais que executam funções passando de um estado para o outro e depois retornando ao estado inicial, por exemplo, para um pulso em nível baixo, o sinal está em nível *ALTO*, passa temporariamente para o nível *BAIXO* e depois retorna ao nível *ALTO*:

![[sd_022.png]]

Perceba que, idealmente teríamos uma passagem instantânea de um estado para o outro, mas na realidade essa passagem dura um certo tempo. O tempo $t_f$ de duração da passagem do nível *ALTO* para o nível *BAIXO* é denominado *fall time* ou **tempo de descida** e o tempo $t_r$ de duração da passagem do nível *BAIXO* para o nível *ALTO* é denominado *rise time* ou **tempo de subida**.

Uma última característica importante dos pulsos é a chamada **largura do pulso**, designada por $t_w$ que representa o tempo entre os instantes onde as bordas de subida e de descida (*rising edge* e *falling edge*) sinal estão a $50\%$ do nível alto de tensão.