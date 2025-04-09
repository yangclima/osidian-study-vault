---
tags:
  - Definição
---
Quando algo de errado ocorre, o interpretador da linguagem **lança uma exceção**, o que normalmente causa a parada imediata do programa, porém, alguns erros são previsíveis e é dever do programador lidar com isso, **tratando a exceção**, isso pode ser feito através de cláusulas de exceção que podem ser trabalhadas através de blocos `try-except`:
```python
dividend = int("Enter the dididend: ")
divisor = int("Enter the divisor: ")

try:
    result = dividend / divisor
except (TypeError, ZeroDivisionError) as errorMsg:
    print("erorMsg")
```
O código crasharia ao tentar realizar uma divisão por zero, porém, não seria um erro no programa, mas sim do usuário, isso é resolvido com o código acima, que ao invés de parar sua execução, simplesmente exibe o texto "The ratio is undefined". 

# Lançando Exceções
As vezes também é útil lançar as nossas próprias exceções, para indicar ao código cliente que algo de errado está acontecendo, por exemplo numa função, fazemos isso com a palavra reservada `raise`:
```python
raise Error("Error log") 
```

# `Assertions`
Os Assertions, muito úteis para construir testes e para Debugar nosso código são declarações que validam uma expressão booleana e caso ela seja falsa, lança um `AssertionError` interrompendo a execução do programa caso não seja tratada e exibindo o log de erro:
```python
assert BooleanExpression, "log"
```