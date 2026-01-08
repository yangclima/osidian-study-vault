Os sistemas digitais em geral, obtêm dados codificados em [[Sistemas de numeração digital|binário]] e outras informações que de formas variadas são submetidos a operações tais como **codificação e decodificação**, **multiplexação**, **demultiplexação**, **comparação**, **conversão de código e barramento de dados**, operações essas que tem sido facilitadas pela aplicação de numerosos tipos de CI's que se enquadram na categoria *Medium Scale Integration* (*MSI*) ou de **Integração de Média Escala**.

Destes, os primeiros circuitos que veremos são os chamados **Decodificadores**, circuitos que recebem uma série de entradas que representa um número binário, as processa, e ativa apenas a saída correspondente ao número recebido, de tal forma que apenas uma saída fica ativa por vez. 

![[sd_039.png|center]]

Perceba que um decodificador com $N$ entradas tem $2^N$ códigos de entrada possíveis, podendo portanto, controlar no máximo $M = 2^N$ saídas, entretanto, são comuns os casos onde $M < 2^N$, ou seja, que o decodificador controle menos entradas do que poderia, nesse caso, é comum que qualquer código recebido nas entradas que não corresponda a nenhum dos valores esperados mantenha todas as saídas desativadas.

Quanto a nomenclatura desses circuitos, um decodificador de $N$ entradas e $M$ saídas é normalmente chamado de *decodificador de $N$ para $M$ linhas* ou *decodificador $1$ de $M$*, ou mesmo *conversor ou decodificador de binário para $M$* (Mais comum para números de saídas específicas como  8 ou "Octal", 10 ou "Decimal"  ou 16 ou "Hexadecimal").

É muito comum que esses sistemas possuam também uma ou mais entradas denominadas *ENABLE* ou **habilitação**, seu papel é garantir o controle sobre o momento em que os decodificadores estão ativos, o que permite, por exemplo, um encadeamento de decodificadores.

Um exemplo comum de decodificador é o **decodificador de BCD para display de 7 segmentos** que apesar de ser comum é uma exceção a nossa regra de que um decodificador ativa uma saída por vez, aqui entretanto, uma combinação de saídas fica ativa por vez.