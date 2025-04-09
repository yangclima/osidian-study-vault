---
tags:
  - Definição
---
A programação orientada ao objeto é um paradigma de programação que permite a construção de blocos de código que representam objetos da vida real, reunindo dados e funções que simulam o seu funcionamento real, permitindo um código mais flexível e reutilizável. A chave para entender a POO é pensar nos objetos como coleções de dados e métodos, sendo usados para modularizar e decompor o nosso código. 

A forma de implementar esse paradigma é através dos tipos de dados abstratos, ou seja, um conjunto de objetos e operações sobre esses objetos. As especificações dessas operações definem uma interface entre o tipo de dado abstrato e o resto do programa definindo o comportamento das operações e criando uma barreira de **abstração** que isola o funcionamento interno da classe, suas implementações e algoritmos do resto do programa. O segredo para aderir eficientemente ao POO é criar tipos de dados abstratos que serão sempre relevantes no contexto do programa. 

No python, a maneira de implementar a abstração de dados e a modularização relacionada a POO são as classes:
```python
import math

class Point:
    """An Point is a poit of cartesian Plane"""
    # The value of the Point is represented by two floats 
    # self.x and self.y your cordinates

    def __init__(self, x: float = 0, float = 0):
        """Create a new Point"""
        self.x = x
        self.y = y

    def distanceOf(self, p: 'Point'):
        """Compute the euclidian distance of two points"""
        return math.sqrt((self.x - p.x)**2 + (self.y - p.y)**2)
```
Perceba que a Docstring no início da classe só dá informações sobre a abstração, não sobre sua implementação, essa é a função dos comentários abaixo dele.

Quando uma definição de função ocorre dentro da definição de uma classe chamamos essa função de ***método*** e essa função passa a estar associada à classe.

Classes no geral suportam dois tipos de operações:
- ***Instanciação***: Se você imaginar a classe como uma forma para a criação de objetos, a instanciação seria justamente a operação de gerar um novo objeto através dessa forma, para criarmos um objeto `p` a partir da classe `Point` faríamos `p = Point()` e `p` seria então uma **instância** da classe `Point`.
- ***Referência de atributos***: As funções e variáveis definidas dentro da classe podem ser chamadas de atributos e acessados usando a chamada *dot notation*. por exemplo `Point.distanceOf` se refere ao método `distanceOf` pertencente a própria classe `Point`, ao declarar, porém, `p.distanceOf` acessaríamos um cópia desse método pertencente a instância `p` de `Point`.
# Instanciação e o método `__init__`
O método `__init__` pertence a um conjunto de métodos especiais chamado de *dunder methods* ou *magic methods* que desempenham funções especiais no contexto das Classes, sendo executados automaticamente em ocasiões específicas para as quais cada um é destinado. No caso do `__init__` sua responsabilidade é controlar a instanciação, é ele que recebe e controla os argumentos passados ao criar uma instância da classe, no caso da nossa classe `Point`, ao declarar `p = Point(3, 2)` é a função `__init__` que recebe os argumentos 3 e 2, e então executa
```python
self.x = x
self.y = y
```
Mas o que realmente  está acontecendo aqui? Perceba que na assinatura da função sempre aparece a palavra `self`, essa palavra é escolhida por convenção e deve ser sempre o primeiro parâmetro na assinatura de qualquer método de instância, é através dele que nós referenciamos a instância dentro dos seus próprios métodos e assim somos capazes de acessar suas variáveis. Sendo assim, no trecho de código acima o que a função faz é criar as **variáveis de instância** (Ou atributos de instância) `x` e `y` e atribuindo a elas os valores dos argumentos.

# Atributos de Classe x Atributos de Instância
Existem dois tipos de atributos: Atributos de classe, que pertencem tanto a própria classe (A forma) quanto a todas as suas instâncias e os Atributos de instância, que são exclusivos de cada instância.