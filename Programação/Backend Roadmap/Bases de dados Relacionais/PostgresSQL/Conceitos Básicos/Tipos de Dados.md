O PostgresSQL tem uma ampla gama de tipos de dados para as mais variadas aplicações e finalidades e permite ainda, a criação de novos tipos de dados com o uso do comando `CREATE TYPE`. 

Esses dados são divididos em diversos tipos, como: Numéricos, Monetários, De Caractere, Binários, Data/Hora, Booleanos, Enumerados, Geométricos e etc, sendo todos eles:

| Name                        | Aliases             | Description                                                                        |
| --------------------------- | ------------------- | ---------------------------------------------------------------------------------- |
| `bigint`                    | `int8`              | Inteiro de 8 bits com sinal                                                        |
| `bigserial`                 | `serial8`           | Inteiro de 8 bits auto incrementado                                                |
| ``bit [(n)]``               |                     | Sequência de bits de tamanho fixo                                                  |
| ``bit varying [(n)]``       | ``varbit [(n)]``    | Sequência de bits de tamanho variável                                              |
| `boolean`                   | `bool`              | Valor lógico binário: (True/False)                                                 |
| `box`                       |                     | Caixa retangular no plano                                                          |
| `bytea`                     |                     | Dados binários                                                                     |
| ``character [(n)]``         | ``char [(n)]``      | Sequência de caracteres de tamanho fixo                                            |
| ``character varying [(n)]`` | ``varchar [(n)]``   | Sequência de caracteres de tamanho variável                                        |
| `cidr`                      |                     | Endereços de rede IPv4 or IPv6                                                     |
| `circle`                    |                     | Círculo no plano                                                                   |
| `date`                      |                     | Uma data no calendário (Dia, Mês e Ano)                                            |
| `double precision`          | `float`, `float8`   | Número de ponto flutuante de precisão dupla (8 bytes)                              |
| `inet`                      |                     | Endereço de host IPv4 or IPv6                                                      |
| `integer`                   | `int`, `int4`       | Inteiro de 4 bytes com sinal                                                       |
| ``interval [fields] [(p)]`` |                     | Intervalo de tempo                                                                 |
| `json`                      |                     | Dados JSON textuais                                                                |
| `jsonb`                     |                     | Dados binários JSON, decompostos                                                   |
| `line`                      |                     | Linha infinita num plano                                                           |
| `lseg`                      |                     | Segmento de reta num plano                                                         |
| `macaddr`                   |                     | Endereço MAC (Media Access Control)                                                |
| `macaddr8`                  |                     | Endereço MAC (Media Access Control)  (EUI-64 format)                               |
| `money`                     |                     | Valor monetário                                                                    |
| ``numeric [(p,s)]``         | ``decimal [(p,s)]`` | Numero exato de precisão configurável                                              |
| `path`                      |                     | Caminho geométrico num plano                                                       |
| `pg_lsn`                    |                     | Numero de sequência de um Log PostgreSQL                                           |
| `pg_snapshot`               |                     | Instantâneo do ID de transação em nível de usuário                                 |
| `point`                     |                     | Ponto geométrico num plano                                                         |
| `polygon`                   |                     | Caminho geométrico fechado num plano                                               |
| `real`                      | `float4`            | Numero de ponto flutuante de precisão  única (4 bytes)                             |
| `smallint`                  | `int2`              | Inteiro de dois bytes com sinal                                                    |
| `smallserial`               | `serial2`           | Inteiro de dois bytes com sinal auto incrementável                                 |
| `serial`                    | `serial4`           | Inteiro de quatro bytes com sinal auto incrementável                               |
| `text`                      |                     | Sequência de caracteres de tamanho variável                                        |
| ``time [(p)]``              |                     | Hora do dia, sem timezone                                                          |
| ``time [(p)]``              | `timetz`            | Hora do dia, com timezone                                                          |
| ``timestamp [(p)]``         |                     | Data e hora, sem timezone                                                          |
| ``timestamp [(p)]``         | `timestamptz`       | Data e hora, com timezone                                                          |
| `tsquery`                   |                     | Prompt de busca textual                                                            |
| `tsvector`                  |                     | Documento de busca tetual                                                          |
| `txid_snapshot`             |                     | Instantâneo do ID de transação em nível de usuário (deprecated; see `pg_snapshot`) |
| `uuid`                      |                     | Identificador único universal                                                      |
| `xml`                       |                     | Dados XML                                                                          |

Grande parte desses tipos são implementados nativamente pelo SQL e simplesmente adotados pelo Postgres.