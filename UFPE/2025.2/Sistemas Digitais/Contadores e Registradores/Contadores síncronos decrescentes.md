Já vimos que para um [[Contador Assíncrono]], para inverter a direção de contagem, ou seja, passar de um contador crescente para um decrescente basta mudar a entradas de clock dos [[Flip-flop J-K com clock|flip-flops]] do tipo borda de descida para o tipo borda de subida, essa lógica, entretanto, não funciona para o[[Contador Síncrono]], porém isso pode ser feito invertendo as entradas que vão para as [[Operação AND|portas AND]], isto é, ao invés de alimentarmos cada porta AND com as saídas normais de cada FF anterior na cadeia, alimentaremos com as saídas investidas, veja a imagem:

![[sd_034.png]]

Usando essa lógica, podemos então criar algum tipo de circuito auxiliar que controle o valor que vai para as portas AND permitindo então controlar a direção da contagem, estabelecemos então uma entrada $Up/\overline{Down}$ que faz esse controle, mantendo a porta em nível *ALTO* as entradas normais vão para as AND e a contagem é crescente, caso contrário (Entrada $Up/\overline{Down}$ em nível *BAIXO*) as entradas invertidas vão para as AND e a contagem é decrescente.

![[UFPE/2025.2/Sistemas Digitais/imagens/sd_035.png|center]]

Esse contador que possui a opção de alternar entre contagem crescente e decrescente é denominado **contador crescente/decrescente** e usamos o seguinte diagrama de estados para o representar:

![[sd_036.png|center]]

Perceba que saem duas setas de cada estado, isso é chamado de **transição condicional** e ilustra o fato da transição entre os estado do contador depender do valor de $Up/\overline{Down}$.