Como vimos, a maioria dos sistemas digitais operam de forma sincronizada com os [[Sinais de Clock e Flip-Flops com clock|sinais de clock]] isso decorre do fato de que a operação nesse modelo é muito mais confiável e previsível, nesse sentido, diferenciamos os *latches* e os *flip-flops* pelo fato de que os flip-flops, ao contrário dos latches, operam sincronizados com o clock. 

![[sd_023.png|center]]

Podemos então detalhar a construção interna desse tipo de flip-flop. Os Flip-flops S-R com clock são construídos da seguinte maneira:

![[sd_024.png|center]]

Constituídos então por 3 circuitos internos:
1. Um **circuito detector de borda**, responsável por criar pulsos curtos nas bordas de subida ou descida do clock, a depender do tipo de transição a ser adotada pelo flip-flop, esse tipo de circuito funciona a partir do tempo de resposta das [[Operação NOT|portas NOT]]: ![[sd_025.png|center]]
2. Um **circuito direcionador de pulsos**, responsável por gerar pulsos em nível baixo ou alto (A depender do tipo de latch usado) quando os pulsos do $S$ ou do $R$ coincidirem com o clock (Atua como um porteiro, fazendo com que o valor de $S$ e de $R$ só passe para o latch quando ocorrer uma transição do clock)
3. O próprio circuito do *latch*, seja um [[Latch com portas NOR]] ou um [[Latch com portas NAND]], note que ao usar um *latch NAND* é preciso utilizar um **circuito direcionador de pulsos** com [[Operação NAND|porta NAND]] para que o pulso seja em *BAIXO*, enquanto ao utilizar um *latch NOR* esse circuito deve ser construído utilizando [[Operação AND|porta AND]] para que o pulso seja em *ALTO*. 