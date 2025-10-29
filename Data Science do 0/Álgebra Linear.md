A [[UFPE/2025.1/Álgebra Linear/Álgebra Linear|Álgebra Linear]] é peça fundamental nos trabalhos que envolvem Data Science e consiste basicamente numa área da matemática que estuda os [[Espaços vetoriais]] e suas peculiaridades, dentre os conceitos mais importantes para a Área de Data Science, estão os [[MIT - Courses/Classical Mechanic/Vetores|Vetores]], e as [[Matrizes]]. 

No que se trata da utilização do Python para criar e lidar com Vetores e Matrizes, existe a possibilidade de os representar sem muito esforço (Mas com pouca eficiência) usando o tipo `list` do Python, porém, a biblioteca `Numpy` (Amplamente utilizada na área de Data Science) possui o tipo `array` que permite realizar com eficiência todas as operações entre matrizes e vetores sem nenhuma dificuldade, este artigo, portanto, aborda como lidar com vetores e matrizes usando esta biblioteca.

# Vetores
Os vetores são, em resumo, pontos em um espaço de dimensão finita e são ótimos para armazenar valores numéricos, se tivermos, por exemplo informações correlacionadas, como `horas_estudadas`, `resumos_feitos` e `flashcards_revisados` relativos a um dia específico, podemos representar essas informações como um vetor:

```python
import numpy as np

dia_1 = np.array([
    3, # Horas estudadas
    4, # Resumos feitos
    2  # Flashcards revisados
])

print(dia_1)
# SAÍDA: [3 4 2]
```

É possível realizar operações entre vetores, a primeira delas é a soma, imagine que, dados os vetores mencionados acima, tenhamos informações sobre três dias distintos e queiramos saber as `horas_estudadas`, `resumos_feitos` e `flashcards_revisados` nesse intervalo de 3 dias, então, podemos obter um `array` representando essas informações através da soma desses três vetores:

```python
import numpy as np

dia_1 = np.array([
    3, # Horas estudadas
    4, # Resumos feitos
    2  # Flashcards revisados
])

dia_2 = np.array([
    5, # Horas estudadas
    7, # Resumos feitos
    3  # Flashcards revisados
])

dia_3 = np.array([
    1, # Horas estudadas
    2, # Resumos feitos
    0  # Flashcards revisados
])

dias_1_a_3 = dia_1 + dia_2 + dia_3

print(dias_1_a_3)
# SAÍDA: [ 9 13  5]
```

Podíamos também, tendo informações sobre dois dias, querer entender se a evolução foi positiva ou negativa, comparando o dia atual (`dia_2`) com o dia anterior (`dia_1`), podemos fazer isso através da subtração (Perceba que tanto na soma quanto na subtração, o que fazemos é basicamente somar/subtrair termo a termo do vetor):

```python
import numpy as np

dia_1 = np.array([
    3, # Horas estudadas
    4, # Resumos feitos
    2  # Flashcards revisados
])

dia_2 = np.array([
    5, # Horas estudadas
    7, # Resumos feitos
    1  # Flashcards revisados
])

evolucao = dia_2 - dia_1

print(evolucao)
# SAÍDA: [2 3 -1]

# Isso indica que estudamos 2 horas a mais que ontem, fizemos
# 3 resumos a mais e revisamos um flashcard a menos
```

Uma outra operação muito importante na álgebra linear é o [[Produto interno|produto escalar]], que, apesar de muito útil é um tanto mais abstrato, o que fazemos basicamente é multiplicar cada componente dos vetores e depois somar tudo, essa operação sempre retorna um valor escalar e pode ser pensada como uma medida da proximidade entre dois vetores, se todos os vetores **tiverem o mesmo tamanho**  (Chamamos o tamanho do vetor de norma, um conceito que já será apresentado) os dois vetores mais parecidos serão aqueles que possuem o maior produto escalar, podemos pensar também no produto escalar como o tamanho que um vetor teria se fosse projetado na direção outro:

```python
import numpy as np

vetor_1 = np.array([1, 3, 9])
vetor_2 = np.array([2, 7, 5])

produto_escalar = np.dot(vetor_1, vetor_2)

print(produto_escalar)
# SAÍDA: 68
```

Um último conceito importante a respeito dos vetores é a sua norma que pode ser pensada como sendo o tamanho desse vetores e pode ser calculado como a raiz do produto vetorial de um vetor por ele mesmo, usando o exemplo de antes, o vetor que tiver a maior norma seria, talvez, o dia mais produtivo:

```python
import numpy as np

dia_1 = np.array([
    3, # Horas estudadas
    4, # Resumos feitos
    2  # Flashcards revisados
])

norma = np.linalg.norm(dia_1)

print(norma)
# SAÍDA: 5.385164807134504
```

# Matrizes
Uma matriz é uma coleção de números bidimensional, podendo assim, ser representada como uma lista de listas, pense numa matriz como um vetor de vetores, usando o exemplo do tópico passado, digamos que temos aquelas informações sobre os últimos três e queremos representar esse intervalo mas sem perder informação sobre cada dia em específico façamos o seguinte, usando ainda o tipo `array` do `Numpy`, podemos criar uma matriz da seguinte forma:

```python
import numpy as np

ultimos_tres_dias = np.array([
    [3, 4, 2], # Dia 01
    [5, 7, 3], # Dia 02
    [1, 2, 0]  # Dia 03
])

print(ultimos_tres_dias)
# SAÍDA: [[3 4 2]
#         [5 7 3]
#         [1 2 0]]
```

Cada matriz tem então uma dimensão (tamanho) $m\times n$ onde $m$ é o seu número de linha e $n$ é seu número de colunas, muitas vezes será útil pensar em cada linha da matriz como vetor de dimensão $n$ e em cada coluna como um vetor de dimensão $m$:

```python
import numpy as np

ultimos_tres_dias = np.array([
    [3, 4, 2], # Dia 01
    [5, 7, 3], # Dia 02
    [1, 2, 0]  # Dia 03
])

segunda_linha = ultimos_tres_dias[1]

terceira_coluna = ultimos_tres_dias[:, 2]

print(segunda_linha)
# SAÍDA: [5 7 3]

print(terceira_coluna)
# SAÍDA: [2 3 0]
```

Também é possível criar matrizes a partir de funções usando a seguinte função do `Numpy` usando como argumentos os índices `i` e `j` de cada elemento (Na verdade o `Numpy` passa como argumento para a sua função uma matriz de mesma dimensão com os índices de cada `i` e uma outra matriz de mesma dimensão com os índices de `j`):

```python
import numpy as np

matriz_gerada = np.fromfunction(lambda i,j: i+j, (3,2), dtype="int")

print(matriz_gerada)
# SAÍDA: [[0 1]
#         [1 2]
#         [2 3]]
```

Além de podermos representar listas de vetores usando matrizes, podemos também representar relações binárias e até mesmo usar um matriz $m\times n$ para representar uma função que mapeia vetores de $n$ dimensões para vetores de $m$ dimensões (Essas funções são chamadas [[Transformações lineares]]). Por fim, uma matriz muito usada é a chamada **Matriz Identidade**, uma matriz quadrada (com o mesmo numero de linhas e colunas) que possui todos os valores na sua diagonal iguais a $1$ e fora dela iguais a $0$, usando `Numpy` podemos construir uma matriz desse tipo facilmente:

```python
import numpy as np

matriz_identidade = np.eye(3,3, dtype="int")

print(matriz_identidade)
# SAÍDA: [[1 0 0]
#         [0 1 0]
#         [0 0 1]]
```