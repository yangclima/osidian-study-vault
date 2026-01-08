Além do [[Latch com portas NOR]] e do [[Latch com portas NAND]], temos um outro tipo de latch, o **latch D** ou **Latch transparente**, seu funcionamento é idêntico ao do [[Flip-flop D com clock]], a diferença aqui é que não utilizamos o circuito detector de borda, assim, o circuito direcionador de pulso recebe uma entrada de sinal denominada **habilitação** ou *enable*, abreviada como *EN* que controla, assim como fazia o clock, a passagem do sinal de $D$ para a saída $Q$, controlando então o valor de saída do latch:

![[sd_028.png|center]]

Note que na representação do latch D, não utilizamos o triângulo como nos flip-flops isso deve-se ao fato de que ele não é disparado por borda.