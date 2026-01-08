Como vimos, tanto o [[Latch com portas NOR]] quanto o [[Latch com portas NAND]] tem um problema: Quando as portas *SET* e *RESET* são pulsadas simultaneamente ele assume um estado de falha ou ambíguo e seu comportamento nesse caso é imprevisível, uma outro tipo de flip-flop, também com clock é pensado para resolver esse problema: O flip-flop J-K.

O flip-flop J-K quando é pulsado simultaneamente nas portas SET e RESET entra no chamado *toggle mode* ou **modo de comutação** e simplesmente inverte o seu estado, ou seja se $Q$ é igual a $1$ se torna $0$ e se for igual a $0$ se torna $1$.

Esse tipo de flip-flop tem a mesma constituição interna que o [[Flip-flop S-R com clock]], um circuito detector de borda, um circuito direcionador de pulsos e um *latch NAND* ou *latch NOR*, a grande diferença é que é feita uma realimentação na circuito direcionador a partir da saída $Q$ no circuito direcionador do *SET* e a partir da saída $\overline Q$ no circuito direcionador do *RESET*:

![[sd_026.png]]

Perceba então que, a passagem do sinal de $J$ (O pulso no *SET* do latch interno) só é permitida quando $\overline Q$ está em *ALTO* e a passagem do sinal de $J$ (O pulso no *RESET* do latch interno) só é permitida quando $Q$ está em *ALTO*, assim, quando tanto $J$ como $K$ estão em *ALTO*, o flip-flop J-K comuta o seu estado, ou seja, inverte os sinais de $Q$ e $\overline Q$.