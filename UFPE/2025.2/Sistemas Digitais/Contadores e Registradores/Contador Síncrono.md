Como vimos, o grande problema do [[Contador Assíncrono]] é o acúmulo dos atrasos dos [[Flip-flop J-K com clock|flip-flops]] ao longo da cadeia o que impossibilita sua aplicação em sistemas de alta frequência, assim introduziremos agora um outro sistema de contador, mais complexo, mas que não apresenta essa limitação já que os flip-flops atuam de forma sincronizada, ou, mais especificamente, o [[Sinais de Clock e Flip-Flops com clock|sinal de clock]] é o mesmo para todos os ff's.

O conceito é simples, como o mesmo clock estará alimentando todo os  flip-flops a divisão de frequência não ocorrerá e portanto precisamos de um mecanismo que orquestre a atualização desses dispositivos o que pode ser feito fazendo com que apenas o primeiro ff esteja constantemente com as entradas  em nível alto e **cada flip-flop da cadeia seja atualizado apenas quando todos os flip-flops anteriores estiverem no nível *ALTO***, o que pode ser garantido utilizando-se [[Operação AND|portas AND]].

![[sd_031.png|center]]

Pode-se notar que, nesse caso, o atraso total não depende do número de ff's e é um valor constante para o circuito, dado por:

$$
\text{Atraso total} = t_{pd} \text{ do FF } + t_{pd} \text{ da porta AND }
$$
