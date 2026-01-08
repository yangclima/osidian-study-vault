# Formatação de espaço em branco
Diferente de outras linguagens que utilizam colchetes para criar blocos de código e delimitar os blocos de código, Python utiliza espaços em branco com uma indentação para realizar essa tarefa, veja:

```python
for i in [0,1,2]:
    print(i) # Primeira linha do bloco 'for i'
    for j in [0,1,2]: 
      print(j) # Primeira linha do bloco 'for j'
    
    print(i) # Última linha do bloco 'for i'
    
print("Hello world!") # Linha fora do for
```

Entretanto, por conveniência, o interpretador Python ignora espaços e quebras de linha dentro de colchetes e parênteses, o que pode facilitar a leitura:

```python
print([
	[0,1,2],
	[3,4,5],
	[6,7,9]
])
```

Quando não temos parênteses mas queremos quebrar uma linha para facilitar a leitura do nosso código podemos quebrar as declarações usando uma barra invertida (' \ ') :

```python
nome = "yan " \
    "guilherme"
    
print(nome) 
# Saída: "yan guilherme"
```

# Módulos
Certos recursos do Python não estão disponíveis por padrão (Pertencem a módulos padrão ou mesmo módulos de terceiros) e para serem acessados precisam ser importados, essa importação pode ser feita da seguinte maneira:

```python
from "<modulo>" import "<recurso>"
```

Podemos também importar o módulo inteiro, da seguinte forma:

```python
import "<modulo>"
```

Algumas vezes o nome do módulo pode ser muito grande e para evitar digitar continuamente esse nome podemos criar um apelido para o módulo:

```python
import "<modulo>" as "<apelido>"
```

O mesmo pode ser feito para recursos específicos:

```python
from "<modulo>" import "<recurso>" as "<apelido>"
```

# Funções 
Funções são como regras que a partir de uma série de entradas gera um determinado resultado, para criar funções em Python utilizamos o seguinte formato:

```python
def <nomeDaFunção>(<argumentos>):
    """<descricaoDaFuncao>"""
    return <value>
```

Para os argumentos podemos também definir valores padrão:

```python
def funcao(arg1="valorPadrao"):
    """descricao"""
    return arg1
```

E em Python podemos criar funções anônimas:

```python
square = lambda x: x**2
```

# Strings
São cadeias de caracteres e devem ser criadas utilizando aspas simples ou duplas:

```python
string = "texto"
string = 'texto'
```

Para escapar caracteres especiais devemos utilizar ' \ ' e se quisermos criar strings que desconsideram o escape de caracteres usamos:

```python
string = r".src\locaL\TESTE.py"
```

# Exceções
Para realizar o tratamento de erros em Python utilizamos as estruturas try-catch, que tem o seguinte formato:

```python
try:
  <bloco>
catch Exception:
  <bloco>
```

# `defaultDict`

O `defaultDict` é um recurso que pertence ao  módulo `collections` muito útil ao criar, por exemplo, acumuladores para contar palavras em um texto ou lista:

```python
from collections import defaultdict

word_counter = defaultdict(int)

# Como arg passamos uma função usada para criar uma nova chave do
# dict caso tentemos acessar uma chave inexistente 
```

# `Counter`

O `Counter` é um recurso, também do módulo `collections` que, dada uma lista, conta a quantidade de itens iguais e cria um dict do tipo:

```python
from collections import Counter

c = Counter(["a", "a", "a", "b", "c"])
# c = {"a": 3, "b": 1, "c": 1}
```

Ele também possui um método chamado `most_common` que retorna os itens mais comuns da lista:

```python
from collections import Counter

c = Counter(["a", "a", "a", "b", "c"])
# c = {"a": 3, "b": 1, "c": 1}

# Retorna os 2 itens mais comuns 
for word, count in c.most_common(2): 
    print(f"{word}: {count}")
```

# Veracidade
Python considera itens como `0`, `[]`, `{}`, `0.0`, `None`, `Null` como se fossem o equivalente ao booleano `False` o que permite utilizar estes nas declarações `if` e também, assim como o JavaScript, possui a avaliação de curto circuito, além disso, possui a função `all` que retorna `True` apenas se todos os itens da lista não são falsos e a função `any` que retorna `True` se qualquer dos seus itens não for falso.