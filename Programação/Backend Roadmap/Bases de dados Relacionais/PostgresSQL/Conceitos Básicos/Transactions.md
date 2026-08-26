Transactions são um conceito fundamental em qualquer [[Introdução e o modelo relacional|SGBD]], e a principal ideia desses objetos é a capacidade de encapsular várias operações um uma única operação atômica de modo que os estágios intermediários de sua execução não são visíveis para transações concorrentes e se alguma etapa falhar impedindo a continuação ou conclusão da transação, nenhuma das etapas da mesma afeta o banco de dados além de que, deve também haver uma garantia de que após a conclusão com sucesso da transação, suas modificações sejam de fato salvas no banco de dados, isso tudo enquanto garante que transações simultâneas sejam feitas e processadas.

No PostgreSQL criamos uma transação utilizando as palavras chave `BEGIN` e `COMMIT`, seguindo a sintaxe:

```SQL
BEGIN;

-- Sequência de passos e consultas da transação

COMMIT;
```

Dentro desse bloco, chamado, por vezes, de bloco de transação, podemos ainda usar o comando `ROLLBACK` para a qualquer momento cancelar a execução da transaction ou, utilizando definições de `SAVEPOINT savepoint_name` usar `ROLLBACK to savepoint_name`
para voltar a um ponto específico da transação.

Na prática, se não especificamos `BEGIN` e `COMMIT`, cada operação, seja update, delete, inserte e etc, será automaticamente executada sozinha em um próprio bloco granular de transação.