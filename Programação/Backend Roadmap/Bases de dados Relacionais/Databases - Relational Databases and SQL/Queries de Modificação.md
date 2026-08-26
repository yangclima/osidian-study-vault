Agora que já vimos a maioria dos aspectos da [[Instrução SELECT básica|Instrução SELECT]], veremos resumidamente a estruturas das queries de modificação de dados, sendo elas `INSERT` (Para inserir uma linha na tabela), `DELETE` (Para remover uma linha da tabela) e `UPDATE` (Para atualizar os valores dos atributos de uma linha da tabela).

A estrutura básica de uma query de `INSERT` é:

```SQL
INSERT INTO <table_name> <attrs>
    VALUES(<attr_1>, <attr_2>, ..., <attr_3>)
```

Por exemplo:

```SQL
INSERT INTO users (name, sector, role)
    VALUES('Yan', 'assessor', 'executivo')
```

A Query de `DELETE`, por sua vez, tem a estrutura:

```SQL
DELETE FROM <table_name>
WHERE <condition>
```

E basicamente remove todas as linhas da tabela que satisfizerem a condição, por exemplo:

```SQL
DELETE FROM users
WHERE name = "Yan"
```

Por fim, a query `UPDATE` ten o formato:

```SQL
UPDATE <table_name> 
SET <att_1> = <value1>, <att_2> = <value2>, ..., <att_n> = <valuen>
WHERE condition
```

Por exemplo:

```SQL
UPDATE users
SET name = 'Yan Guilherme', role = 'riretor', sector = 'comercial'
WHERE name = 'Yan'
```

