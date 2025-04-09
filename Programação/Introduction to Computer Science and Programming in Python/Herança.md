---
tags:
  - Definição
---
A Herança é um dos pilares da [[POO e Classes|Programação Orientada a Objetos]], ela permite a criação de uma hierarquia de tipo e a criação de grupos de objetos relacionados, em Python a herança entre classes é definida da seguinte forma:
```python
class Animal:
    def __init__(self, name: str):
        self.name = name

    def eat(self, food: str) -> None:
        print(f"The {self.name} is eating {food}.")
        
    def live(self) -> None:
        print(f"The {self.name} is living.")

class Dog(Animal):
    def __init__(self, breed: str):
        super().__init__("Dog")
        self.breed = breed

	def bark(self):
	    print(f"{self.name} - The {self.breed} is barking: Wolf!")

    def eat(self, food: str) -> None:
        print(f"The {self.breed} is eating {food}")

class Pug(Dog):
    def __init__(self, age: int):
        super().__init__("Pug")
        self.age = age

```
Na código acima a classe `Dog` é filha, ou seja, está herdando da classe `Animal` isso permite a ela ter acesso a todos os métodos e variáveis de classe da classe mãe, bem como sobrescrever os seus métodos para definir o próprio comportamento, instanciando a classe filha teríamos algo como:
```python
brutus = Dog("Yorkshire")
rex = Pug(2)

brutus.bark()
# Out: Dog - The Yorkshire is barking: Wolf!

brutus.live()
# Out: The Yorkshire is eating beef.

brutus.eat("beef")
# Out: The Dog is living.

print(rex.name)
# Out: Dog
```
Podemos notar várias coisas a partir disso: 
- A classe filha (`Dog`) pode implementar os próprios métodos, visto que implementou o método `bark`;
- A classe filha pode acessar as variáveis e métodos da classe mãe, visto que acessou a variável `self.name` mesmo sem ter diretamente essa variável e possui o método `live` que não foi definido na própria declaração;
- A classe filha inicializa uma espécie de instância interna da classe mãe dentro do seu inicializador (método `__init__`) acessando-a através da palavra reservada `super` , uma referência direta a classe mãe;
- A classe filha pode sobrescrever métodos da classe mãe, substituindo-os, como fez com o método `eat`
- Existe herança múltipla, já que a classe filha da classe filha tem acesso a variáveis e métodos que pertencem ao que seria a classe "avó"
# Função `isinstance`
A função `isinstance` é uma [[Funções|função]] built-in do python que permite checar se um objeto é uma instância de uma classe ou de uma classe que herda de outra, a expressão `isinstance(rex, Animal)` retornaria `True`, bem como `isinstance(rex, Dog)` e `isinstance(rex, Pug)`, mas retornaria `False` para `isinstance(brutus, Pug)`