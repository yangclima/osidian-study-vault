O circuito mais simples possível para um flip-flop é feito com duas portas [[Operação NAND|NAND]] interconectadas da seguinte maneira:

![[sd_019.png|center]]

Essa versão é também chamada de *latch NAND* e, nesse caso, as portas *SET* e *RESET* estão normalmente em nível *ALTO* e a alteração do seu estado é feita **pulsando** as entradas em nível *BAIXO*, ou seja, pulsando *SET* alteramos $Q$ para $1$ e pulsando *RESET* alteramos $Q$ para $0$.

Uma outra condição, dessa vez, indesejada, é obtida quando pulsamos em nível *BAIXO* ambas as entradas *SET* e *RESET* simultaneamente, nesse caso, tanto $Q$ quanto $\overline Q$ assumem o valor $1$.

Uma representação alternativa do **latch NAND**, também chamado de **latch S-R** é a seguinte:

![[sd_020.png|center]]

Uma aplicação importante do *latch NAND* é evitar o *contact bounce* ou **trepidação de contato** em chaves mecânicas.