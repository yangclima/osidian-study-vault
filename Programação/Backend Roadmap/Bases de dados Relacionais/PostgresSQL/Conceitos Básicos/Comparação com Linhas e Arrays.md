Uma linha no PostgreSQL representa um único e individualmente identificável registro com uma série de atributos em uma tabela, cada um composto por um conjunto de colunas onde cada uma armazena um [[Tipos de Dados|tipo específico de dado]] determinado pela estrutura da tabela em si.

Existem múltiplos operadores e constructs que podem ser usados para comparar linhas e grupos de valores, alguns dos quais serão apresentados aqui.

> A diferença entre `(value [,...])` e `(array expression)` é que a primeira pode ser qualquer tipo de lista de valores com valores de qualquer tipo, enquanto a segunda é um tipo homogêneo de conjunto (dados sempre do mesmo tipo).

# Operador `IN`
O operador `IN` compara uma `expression` com todos os valores de uma determinada de tal forma que basicamente verifica e retorna `true` apenas se `expression` estiver presente no grupo de valores, seguindo a sintaxe:

```SQL
expression IN (value [,...])
```

De forma similar, podemos verificar se um valor NÃO está presente em um conjunto com:

```SQL
expression NOT IN (value [,...])
```

# Operador `SOME` ou `ANY`
O operador `ANY`, sinônimo de `SOME`, basicamente compara utilizando um operador especificado, um valor, também especificado, contra todos os valores de um conjunto, retornado true caso qualquer uma das comparações retorne `true`, seguindo a sintaxe:

```SQL
expression operator ANY (array expression)
```

```SQL
expression operator SOME (array expression)
```

# Operador `ALL`
O operador `ALL` basicamente compara uma expressão fornecida utilizando um operador especificado e retorna `true` se, e somente se, todas as comparações retornarem `true`, seguindo a sintaxe;

```SQL
expression operator ALL (array expression)
```

# Comparação de construtores de Linha
Construtores de linha são uma sintaxe especial do `SQL` utilizada para criar basicamente linhas, por exemplo:

```SQL
SELECT ROW(value [,...])
```

Esses construtores podem ser comparados utilizando qualquer operador, seguindo a sintaxe

```SQL
row_constructor operator row_constructor
```

Que basicamente compara cada valor das linhas sequencialmente, o primeiro do primeiro com o primeiro do segundo, o segundo do primeiro com o segundo do segundo e assim por diante.

Existe ainda o operador `IS DISRINCT` que retorna true se a comparação valor a valor retornar `false` para cada valor da lista:

```SQL
row_constructor IS DISTINCT row_constructor
```

Ou, o contrário

```SQL
row_constructor NOT IS DISTINCT row_constructor
```