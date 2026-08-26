Quando você está construindo e rodando sua aplicação sobre uma camada de banco de dados a  última coisa com a qual você quer se preocupar é a integridade dos dados, felizmente, as implementações modernas, como o próprio POSTGRES já fazem isso por nós, tomando medidas especiais no que se refere a isso através da implementação de modelos transacionais como o ACID.

Uma transaction numa database é uma série de operações logicamente agrupadas, por exemplo, de forma abstrata: "Insira uma linha aqui, atualize um registro lá" e etc. qualquer aplicação que opera sobre um banco de dados faz isso constantemente, o problema é que muitas coisas podem dar errado no caminho se uma única consulta retornar erro e toda aplicação pode ser comprometida por isso, de forma que cada tipo de erro recebe um nome especial e é importante conhecê-los:

1. `Dirty Reads`: Esse erro ocorre quando uma transaction está tentando atualizar um registro no banco de dados e antes que ele conclua a operação uma outra transação consulta o valor que está sendo atualizado, recebendo o valor desatualizado
2. `Non-Repeatable Reads`: Esse erro ocorre quando uma transaction faz duas leituras consecutivas mas uma outra transaction concorrente realiza e conclui uma atualização no dados entre as duas leituras gerando uma inconsistência
3. `Phantom Reads`: Semelhante ao anterior, esse erro ocorre quando uma transaction faz duas leituras consecutivas mas antes da segunda, uma outra transaction insere dados na tabela, gerando uma leitura fantasma, mais uma vez, uma inconsistência.

Para evitar esses erros e outros é que o ACID existe. ACID é um acrônimo para Atomicity (Atomicidade), Consistency (Consistência), Isolation (Isolamento) e Durability (Durabilidade):

- **Atomicidade** se refere ao fato de cada transaction ser interpretada como uma operação individual, de modo que ou temos um sucesso completo ou uma falha completa, sem transações parcialmente realizadas
- **Consistência** se refere ao fato de que os dados se mantem consistentes antes e depois de uma transaction, sem etapas ausentes
- **Isolamento** vem do fato de múltiplas transactions poderem ocorrer de maneira simultânea sem que nenhuma leitura errada seja feita
- **Durabilidade** o sucesso de uma transação é robusto contra falhas do sistema

Em geral, uma database em conformidade com os princípios ACID, garante então que as transações ocorram e falhem sem ferir a integridade dos dados e que múltiplas transações ocorram simultaneamente sem interferir uma na outra.

Para aplicar esses princípios os sistemas de bancos de dados usam um sistema chamado **Locking** que mantém os dados alvo da transaction bloqueados contra modificações e acessos até a finalização do processo, ou seja, bloqueando transações concorrentes, além disso, após bloquear os dados alvo, a transação roda numa espécie de Dry Run, modifica suavemente os dados mas as alterações só são confirmadas e salvas quando a transação é concluída com sucesso, sendo descartadas caso contrário.

Em geral, bancos de dados NoSQL são construídos como sistemas distribuídos e nesse caso, você nunca pode ter completa consistência e completa disponibilidade, tornando o ACID inalcançável nesse tipo de sistema, uma padrão então estabelecido para esse tipo de sistema chama-se BASE o que significa:

1. **Basic Availability**: A database funciona na maior parte do tempo, mesmo que não perfeitamente
2. **Soft-State**: Não há necessariamente consistência entre os nodes da database durante 100% do tempo
3. **Eventual Consistency**: Os dados acabarão por ficar consistentes entre os nós, por exemplo, no momento da leitura.

