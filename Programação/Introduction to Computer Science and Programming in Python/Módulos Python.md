Grandes projetos de código requerem a contribuição de, às vezes, dezenas de programadores, imagine que inferno seria se, todo o código, isto é, milhares e milhares de linhas de código estivessem escritas no mesmo arquivo, trabalhar simultaneamente seria totalmente inviável, é por isso, que o python provê uma grande facilidade nesse sentido: Os módulos. 

Os módulos permitem, assim como as [[Funções|funções]], a aplicação da decomposição, nos permite segregar o nosso código em pedaços e acessar sempre que necessário esses pedaços de nosso código.

Um módulo python é o código escrito em um arquivo `.py`, no exemplo a seguir criamos um módulo chamado `circle.py`:
```python
pi = 3.1415

def area(radius: float) -> float:
    return pi * radius**2

def circumference(radius: float) -> float:
    return 2.0 * pi * radius

def sphere_surface(radius: float) -> float:
    return 4.0 * area(radius)

def sphere_volume(radius: float) -> float:
	raturn (4.0/3.0) * pi * radius**3
```
Caso precisemos utilizar as variáveis e definições desse módulo num outro, podemos importá-lo no outro módulo e acessá-las através da *dot notation*, veja:
```python
import circle

print(circle.pi)
# Saída: 3.1415

print(circle.area(2))
# Saída: 12.566
```
É possível acessar também as definições do módulo sem usar *dot notation*, da seguinte forma:
```python
from circle import *

print(pi)
# Saída: 3.1415

print(area(2))
# Saída: 12.566
```
Ou, caso seja necessário, importar apenas determinados itens de um módulo:
```python
from circle import pi, area

print(pi)
# Saída: 3.1415

print(area(2))
# Saída: 12.566
```