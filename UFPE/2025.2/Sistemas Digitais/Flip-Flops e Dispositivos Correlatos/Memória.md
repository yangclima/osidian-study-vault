Os [[Projetando Circuitos Lógicos Combinacionais|circuitos lógicos]] estudados até agora são considerados circuitos lógicos combinacionais,  pois a sua saída num dado instante do tempo, depende apenas dos valores das suas entradas naquele dado instante, a maioria dos circuitos digitais, entretanto, são formados por uma operação conjunta entre esse tipo de circuito e outros circuitos que possuem algo fundamental: **Memória**.

Dentre os elementos que possuem essa característica peculiar, os mais importantes são indiscutivelmente os chamados **flip-flops**. Embora uma porta lógica não possua, por si só, memória, podemos combiná-las utilizando um importante conceito de engenharia denominado **Realimentação** construindo circuitos que então, a possuam.

![[sd_018.png]]

Na imagem acima, vemos a representação genérica de um flip-flop, apresentando duas saídas, denominadas $Q$ e $\overline Q$, a primeira, é também chamada de **saída normal do flip-flop** e sempre que nos referimos ao **estado do flip-flop** estamos tratando do valor de $Q$, a segunda ($\overline Q$) é denominada **saída invertida do flip-flop** e assumimos sempre que ela está no estado oposto que $Q$.

1. O estado *ALTO* do flip-flop é também chamado de *SET* e chamamos a operação de mudar o estado do flip-flop para alto de *setar* o flip-flop.
2. O estado *BAIXO* do flip-flop é também chamado de *CLEAR* ou *RESET* e chamamos a operação de mudar o estado do flip-flop para baixo de *resetar* o flip-flop.

