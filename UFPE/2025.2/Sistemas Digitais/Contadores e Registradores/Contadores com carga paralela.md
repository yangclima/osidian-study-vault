É muito comum em CI's digitais de [[Contador Síncrono|contadores]] a presença de um circuito auxiliar que permite que a qualquer momento, ou em sincronia com o clock, possamos mudar a saída do contador para um valor específico desejado, essa ação é normalmente chamada de *preset* ou **carga paralela** e contadores com essa possibilidade são denominados *presettable* ou **contadores com carga paralela**.

Esse mecanismo pode ser facilmente implementado utilizando as [[Entradas assíncronas]] dos FF's, a ideia é alimentar simultaneamente as entradas $PRE$ e $CLR$ com valores opostos quando a entrada $PL$ (*preload*) for pulsada, configurando individualmente cada [[Flip-flop J-K com clock|flip-flop]] para o valor do bit respectivo na entrada de dados paralelos, o controle do momento onde esses valores serão passados para os FF's é feito por um circuito direcionador controlado pela entrada $PL$.

![[sd_037.png|center]]

Dessa maneira temos o que chamamos de carga paralela assíncrona, independente do sinal de clock, porém muitos CI's tem carga paralela síncrona, ou seja, dependente do [[Sinais de Clock e Flip-Flops com clock|sinal de clock]].