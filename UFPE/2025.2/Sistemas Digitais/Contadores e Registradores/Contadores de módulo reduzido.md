Para muitas aplicações, precisamos de [[Contador Síncrono|contadores]] que possuam módulo diferente do padrão $MOD = 2^N$, o que é extremamente fácil de se fazer utilizando as [[Entradas assíncronas]] dos [[Flip-flop J-K com clock|flip-flops]], no caso, a entrada $RST$. A ideia é detectar quando as saídas dos ff's são compatíveis com um determinado valor, o qual você quer usar para limitar a saída do contador, quando a igualdade for satisfeita, as entradas de controle assíncronas $RST$ dos flip-flops devem ser ativadas, o que pode ser alcançado com uma  [[Operação NAND|porta NAND]], caso as entradas sejam ativas em *BAIXO*, ou com uma [[Operação AND|porta AND]], caso sejam ativas em *ALTO*.

![[sd_032.png|center]]


Na figura acima, por exemplo, o contador é resetado quando $C$ e $B$ estão em *ALTO*, ou seja, quando o contador estiver marcando $11X$ (O valor de $A$ não importa - *Don't care*), quando isso ocorrer o contador é resetado, ou seja, esse contador tem $MOD = 6$, já que possui $6$  estados.

O funcionamento desses circuitos pode ser descrito utilizando um diagrama simples denominado **diagrama de estados**:

![[sd_033.png|center]]