Os  [[Tipos de Dados]] da classe dos tipos numéricos consistem basicamente em inteiros de dois, três, quatro e oito bytes, números de ponto flutuante de quatro ou oito bytes e decimais de precisão selecionável.

| Nome               | Tamanho  | Descrição                                    | Range                                                                 |
| ------------------ | -------- | -------------------------------------------- | --------------------------------------------------------------------- |
| `smallint`         | 2 bytes  | inteiro de pequeno intervalo                 | -32768 até +32767                                                     |
| `integer`          | 4 bytes  | inteiro padrão                               | -2147483648 até +2147483647                                           |
| `bigint`           | 8 bytes  | inteiro de amplo intervalo                   | -9223372036854775808  até +9223372036854775807                        |
| `decimal`          | Variável | exato com precisão especificada pelo usuário | Até 131072 antes do ponto decimal e até 16383 dígitos depois do ponto |
| `numeric`          | Variável | exato com precisão especificada pelo usuário | Até 131072 antes do ponto decimal e até 16383 dígitos depois do ponto |
| `real`             | 4 bytes  | Precisão variável, impreciso                 | 6 dígitos de precisão decimal                                         |
| `double precision` | 8 bytes  | Precisão variável, impreciso                 | 15 dígitos de precisão decimal                                        |
| `smallserial`      | 2 bytes  | Pequeno inteiro autoincrementado             | 1 até 32767                                                           |
| `serial`           | 4 bytes  | Inteiro autoincrementado                     | 1 até 2147483647                                                      |
| `bigserial`        | 8 bytes  | Grande inteiro autoincrementado              | 1 até 9223372036854775807                                             |

# Números inteiros
Os tipos inteiros são `smallint`, `integer` (Ou `int`) e `bigint` e basicamente armazenam números sem parte fracionária, sendo o `integer` a opção mais balanceada, o `smallint` usado somente quando o armazenamento é restrito e `bigint` para armazenar valores que não cabem no `integer`.

# Números de precisão arbitrária
O type `numeric` pode armazenar números com um número enorme de dígitos, utilizados quando precisamos de uma alta precisão, operações entre valores com esse tipo são realizadas de forma exata, sempre que possível, porém costumam ser muito mais lentas que operações entre inteiros ou números de ponto flutuante.

Esse tipo de número tem como atributos uma ``scale``, que corresponde ao número de dígitos após a vírgula e uma `precision` que refere-se a soma do número de dígitos antes da virgula com o número de dígitos depois da vírgula, para uma dada coluna que possui o tipo `numeric` tanto a máxima precisão quanto a máxima escala podem ser especificadas de  modo que números que não se encaixam na restrição são convertidos no momento do update ou insert, desse modo, declaramos esse type como:

```SQL
NUMERIC(precision, scale)
```

Ou, utilizando:

```SQl
NUMERIC(precision)
```

Criamos um número com `scale` 0 (Um inteiro, basicamente) e precisão especificada, enquanto usando:

```SQL
NUMERIC
```

Criamos basicamente um numérico irrestrito, que, além disso, aceita os valores abstratos `NaN`, `Infinity` e `-Infinity` que funcionam algebricamente como se espera, para usar esses valores especiais, os declaremos entre aspas simples nas queries.

# Números de ponto flutuante
Os números de ponto flutuante (|`real` e `double precision`) são muito mais eficientes em armazenamento e cálculo que o type numeric, porém, por conta do formato de mantissa e suas restrições esse tipo é inexato, em especial para números muito pequenos ou muito grandes e implementações que utilizam esse type devem ser cuidadosamente planejadas. Vale notar que esse tipo também permite os valores abstratos ``NaN``, ``Infinity`` e ``-Infinity``.

# Números Seriais
Os números seriais (`smallserial`, `serial` e `bigserial`) não são tipos de dados propriamente ditos, mas uma forma fácil de criar identificadores sequenciais no PostgreSQL e funcionam como um alias que determina que a coluna será `NOT NULL` e que o seu valor padrão será o próximo número da sequência (Com algumas ressalvas, algumas vezes podemos ter furos na sequência, já que uma query incompleta pode consumir o próximo número da sequência mesmo sem ser de fato inserida).
