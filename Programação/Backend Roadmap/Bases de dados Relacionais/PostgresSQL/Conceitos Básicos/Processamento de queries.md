Quando uma query é submetida a um servidor PostgreSQL o objetivo do servidor é respondê-la com uma conjunto de dados. A query SQL define o que retornar mas não como isso será retornado de modo que esta requisição passará por uma série de estágios que permitirão devolver o resultado correto o mais eficientemente possível.

Em ordem de execução, esses estágios são:
1. Parsing
2. Transformation
3. Planning
4. Execution
# Parsing
E etapa de parsing é responsável por verificar a validade e integridade da query e montar uma árvore de execução e possui duas partes principais:

1. . `scan.l` O analisador léxico, que reconhece identificadores e palavras chaves SQL, cada um dos quais dispara um token a ser criado e analisado pelo parser
2. `gram.y` Composta por uma série de regras gramáticas e suas correspondências, analisa os tokens gerados por `scan.l` quanto a sua validade e integridade

o parser, como parte da execução de sua tarefa monta a árvore de query separando a consulta em múltiplas partes identificáveis agrupadas em:

- **Command Type:** Define a estratégia principal que o executor vai adotar.
- **Range Table Entry (RTE):** É o array `rtable`. Cada tabela, view ou subquery mencionada no `FROM` e no `JOIN` vira um elemento aqui, indexado por um número inteiro (o `varno`).
- **Result Relation:** Essencial para comandos de escrita (`INSERT`, `UPDATE`, `DELETE`). Indica o índice da `rtable` que sofrerá a alteração física nos blocos de disco.
- **Target List (`targetList`):** É a lista de expressões que define a "saída" ou o "alvo" da operação.
	- No `SELECT`, são as colunas projetadas.
    - No `UPDATE`, são os novos valores que serão gravados nas colunas.
- **Qualification (`qual`):** Corresponde diretamente à cláusula `WHERE`. É uma árvore de expressões booleanas (ex: `id > 10 AND status = 'ativo'`) que filtra quais tuplas devem prosseguir na árvore de execução.
- **Join Tree (`jointree`):** Estrutura que dita como as tabelas da `rtable` estão conectadas e em qual ordem lógica os filtros e junções (`INNER`, `LEFT`, etc.) se aplicam.

# Rewriter
A saída do parser é passada para a etapa de ``transformation``  que, como esperado, reescreve a query levando uma série de regras em consideração e passa a query modificada para a próxima etapa.

# Planning
Na etapa de planning o objetivo é pegar a query modificada e encontrar o melhor plano de execução para ela, o sistema faz isso automaticamente criando vários planos diferentes, avaliando cada um deles e montando um plano de custo que avalia o custo físico de realizar cada um e seleciona o mais barato, como seria impraticável testar todos os planos possíveis para cada query, uma série de algoritmos e heurísticas definem um limite para os planos a serem testados de modo que o plano final escolhido pode não ser o plano ótimo, porém será razoavelmente otimizado.

Esse plano custo se baseia em estatísticas a respeito das tabelas que são automaticamente armazenadas em `pg_statistic` pelo chamado `autovacuum`, no caso dessa feature estar desativada podemos atualizar as estatísticas manualmente com o comando `ANALYZE`.
# Executor
A partir do plano otimizado definido, a última etapa, o executor, entra em ação, operando recursivamente sobre o plano para extrair o conjunto necessário de linhas da relação alvo devolvendo a cada node do plano uma linha ou um report back que indica a finalização da execução.

- Para o `SELECT` o executor retorna o conjunto de linhas para o cliente como resultado da execução.
- Para o `INSERT` cada linha retornada é inserida na tabela especificada, o que é feito num plano superior de alto nível chamado ``ModifyTable``
- Para o `UPDATE`, cada linha computada inclui todos os valores atualizados mais o id da linha alvo. Os dados são enviados para um nó de ``ModifyTable`` que cria uma linha atualizada e marca a antiga como deletada 
- Para o `DELETE` a única coluna retornada pelo plano é o Id da linha a ser excluída, que será passado para ``ModifyTable`` que marcará a linha como deletada.

![[sql_001.png]]

Nesse contexto de processamento de queries, um comando extremamente útil é o comando `EXPLAIN`, usado para exibir o plano de execução de query permitindo que vejamos como o PostgreSQL executa cada statement e também estatísticas sobre isso e cuja sintaxe padrão é

```SQL
EXPLAIN [ (parameter [, ...] ) ] statement
```

Onde `parameter` pode ser qualquer um ou vários de `ANALYZE`, `VERBOSE`, `COSTS`, `BUFFERS` e `FORMAT`.

`ANALYZE` Executa a query e retorna o query plan mas descartando o resultado da query, podemos testar então usando um comando como 

```SQL 
BEGIN;

EXPLAIN ANALYZE 
    SELECT 
        * 
    FROM 
        users 
     WHERE 
        name LIKE '%Yan%' LIMIT 1;

ROLLBACK;
```

Que não modificará a base de dados.

`VERBOSE` retorna uma série de informações extras como a lista de colunas de output para cada nó no plano de execução o nome de cada trigger para o qual as estatísticas serão exibidas e etc.

`COSTS` inclui os custos estimados de inicialização e o custo total mais o número estimado de linhas bem como o tamanho estimado de cada linha.

`BUFFERS` que só pode ser usado junto com `ANALYZE` e que retorna um resumo de quanto da resposta à query foi do cache do banco de dados e quanto foi do disco propriamente.

`FORMAT` simplesmente define o formato de saída da query, como `TEXT` (Padrão), `YAML`, `JSON` ou mesmo `XML`.