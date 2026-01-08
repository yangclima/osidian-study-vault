Como vimos, a grande maioria dos [[Decodificadores]] recebe uma série de entradas das quais, múltiplas pode estar simultaneamente ativas e apenas uma de suas saídas deve estar ativa por vez, agora veremos os **codificadores** que, como o nome sugere, realizam o processo inverso.

Os codificadores são circuitos digitais com $M$ entradas das quais apenas uma deve estar ativa por vez e cada uma dessas entradas deve ativar uma combinação ou código de saída de $N$ bits.

![[sd_040.png|center]]

Uma das desvantagens dos codificadores simples é que sua lógica pode permitir que, se mais de uma entrada for ativada por vez, a saída possa ser um código inválido ou inesperado, por isso existem os chamados **codificadores de prioridade**, circuitos que possuem a lógica interna necessária para que, caso mais de uma entrada seja ativada por vez, a maior se sobressaia ou seja, tenha prioridade sobre as outras e apenas o seu código seja enviado para a saída.

Uma das aplicações desses circuitos são os chamados *codificadores de chaves*, imagine que uma chave é ligada em cada uma das entradas do circuito e suas saídas conectadas a um decodificador, assim podemos pensar em aplicações como o teclado de sua calculadora.