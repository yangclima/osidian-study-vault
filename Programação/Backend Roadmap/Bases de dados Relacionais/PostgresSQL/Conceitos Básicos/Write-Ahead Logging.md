O Write Ahead Logging (WAL) é o método padrão para garantir a integridade dos dados e resumidamente, seu conceito central é a ideia de que devemos registrar um log sobre cada ação performada antes de performar realmente a ação, escrever de fato os registros nas files do banco de dados, o que fornece uma resistência a falhas do sistema, já que se algo der errado podemos recuperar as ações não performadas a partir desses logs, a chamada `roll-foward recovery` ou simplesmente `REDO`.

A aplicação do WAL resulta numa redução significativa do número de escritas em disco já que apenas os logs do WAL precisam ser escritos para garantir que uma [[Transactions|transação]] seja salva ao invés de todos dados alterados pela transação, além disso, pelo fato do WAL ser escrito sequencialmente ele representa um custo consideravelmente menor de sincronização.

Assim, quando um problema ocorre, basta dar rollback para um backup anterior e então reaplicar sobre ele cada registro de transação do WAL alcançando a consistência de dados novamente, ou, no caso de um `crash-recovery`, checar a última declaração de consistência da database, aplicar WAL em rollback até lá e depois um `rollfoward`.

