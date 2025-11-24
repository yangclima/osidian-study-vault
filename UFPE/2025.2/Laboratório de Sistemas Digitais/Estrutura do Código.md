Um trecho independente de código VHDL é composto por pelo menos 3 seções fundamentais: 
- `LIBRARY`: Contém as declarações de todas as bibliotecas que serão usadas no design.
- `ENTITY`: Especifica os pinos de entrada e saída do circuito.
- `ARCHITECTURE`: É o código VHDL propriamente dito e descreve como o circuito deve se comportar.
# Declarações `LIBRARY`
Uma **biblioteca** é uma coleção de pedaços de código comumente usados, colocar esses pedaços juntos numa biblioteca é o que permite que eles sejam reusados e compartilhados entre diferentes designs, dado esse interesse, o código VHDL é escrito na forma de `FUNCTIONS`, `PROCEDURES` ou `COMPONENTS` que são colocados dentro dos chamados `PACKAGES` que são então compilados na forma da biblioteca em questão.

Para declarar uma biblioteca, isto é, torná-la visível e disponível para a utilização, são necessárias duas linhas de código, uma contendo o nome da biblioteca desejada e outra contendo um cláusula `USE` que especifica a parte específica dessa biblioteca que você deseja importar, por exemplo:

```VHDL
LIBRARY library_name;
USE library_name.package_name.package_parts;
```

Num Design VHDL comum, normalmente são utilizadas pelo menos $3$ bibliotecas:

- `std` a biblioteca VHDL padrão de recursos
- `work` a biblioteca onde você salva seus designs, ou seja, arquivos `.vhd` mais os arquivos criados pela compilação e etc.
- `iee` a biblioteca de recursos padrão da IEEE

Entretanto, as bibliotecas `std` e `work` já estão disponíveis por padrão, nesse caso, nós só precisamos declarar a biblioteca `ieee`.

A biblioteca `ieee` possui diversos `PACKAGES`, dentre os quais, os mais importantes, são:
- `std_logic_1164`: Especifica ``STD_LOGIC`` (8 níveis) e ``STD_ULOGIC`` (9 níveis) sistemas lógicos multivalorados.
- ``std_logic_arith``: Especifica os tipos de dado ``SIGNED`` e ``UNSIGNED`` e as operações aritméticas e de comparação associadas. Também contém várias funções de conversão, que permitem que um tipo seja convertido em outro: ``conv_integer(p)``, ``conv_unsigned(p, b)``, ``conv_signed(p, b)``, ``conv_std_logic_vector(p, b)``.
- ``std_logic_signed``:Contém funções que permitem operações com dados ``STD_LOGIC_ VECTOR`` a serem processadas como se esses fossem do tipo ``SIGNED``.
- ``std_logic_unsigned``: Contém funções que permitem operações com dados ``STD_LOGIC_VECTOR`` a serem processadas como se esses fossem do tipo ``UNSIGNED``.

Destes, o mais utilizado é o `std_logic_1164`, assim, declaramos:

```VHDL
LIBRARY ieee;
USE ieee.std_logic_1164.all;
```

# Declarações `ENTITY`
As declarações `ENTITY`, como vimos, estabelecem os pinos de entrada e saída do nosso design e possuem a seguinte sintaxe:

```VHDL
ENTITY entity_name IS
PORT (
  port1_name: signal_mode signal_type;
  port2_name: signal_mode signal_type;
  ...
  portN_name: signal_mode signal_type
);
END entity_name;
```

O primeiro ponto para se atentar é que o `entity_name` deve ser igual ao nome do arquivo `.vhd` em que criamos o nosso design e que o `VHDL` é case-insensitive, ou seja, não diferencia letras maiúsculas e minúsculas, além disso, o último pino declarado no `PORT` não é finalizado com ponto e vírgula, o que costuma confundir.

Agora começaremos a destrinchar a nossa sintaxe:
- O `signal_mode`, é o modo em que o pino irá operar, e possui $4$ valores possíveis, `IN` e `OUT` onde o pino irá operar em uma única direção, como entrada (`IN`) ou como saída (`OUT`), `INOUT` onde o pino opera em duas direções (entrada e saída) e `BUFFER`, onde o pino opera em uma única direção (saída) mas seu valor pode ser lido internamente.
- O `signal_type` é propriamente o tipo do sinal recebido, pode ser `BIT`, `STD_LOGIC`, `STD_LOGIC_VECTOR`, `INTEGER` e etc.

Um exemplo real, seria:

```VHDL
ENTITY xor_gate IS
PORT(
  a,b: IN BIT;
  s: OUT BIT
);
END xor_gate;
```

Nesse caso, estamos declarando dois pinos de entrada (`a` e `b`) que recebem valores do tipo `BIT` e um pino de saída (`c`) que envia valores do tipo `BIT`.
# Declarações `ARCHITECTURE`
As declarações `ARCHITECTURE` são onde a mágica realmente acontece, é ela que define como o seu circuito deve se comportar, sua sintaxe é a seguinte:

```VHDL
ARCHITECTURE architecture_name OF entity_name IS
  [Declarations]
BEGIN
  [Code]
END architecture_name;
```

Perceba que ela é dividida em duas partes, as declarações (opcional), onde poderemos definir as nossas variáveis auxiliares, constantes, entre outros e o código, onde de fato descreveremos o comportamento do circuito