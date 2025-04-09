Assim como strings, tuplas são sequências ordenadas de elementos, porém, diferente das strings, nas tuplas os itens não precisam ser caracteres e podem pertencer qualquer tipo, inclusive tuplas. Tuplas podem ser criadas através de uma lista de elementos separados por vírgula dentro de parênteses:
```python
tupla = (1, "Hello", "World", ('a', 'b', 'c'), [0, 1])
```
É possível também indexar, repetir, fatiar e concatenar tuplas:
```python
index = ('a', 'b', 'c', 'd')[2]
# Out: 'c'

repet = ('a',) * 3
# Out: ('a', 'a', 'a')

concat = ('a', 'b') + ('c', 'd')
# Out: ('a', 'b', 'c', 'd')

slic = ('a', 'b', 'c', 'd')[1:4]
# Out: ('b', 'c', 'd')
```
É muito útil, quando sabemos o tamanho exato de uma tupla, usar o que chamamos de atribuição múltipla, que consiste em atribuir valores a mais de uma variável simultaneamente:
```python
x, y = (1,2)
# x recebe o valor 1 e y recebe o valor 2
```
Isso é muito útil pois pode ser usado para construir funções que retornam mais de um valor, por exemplo:
```python
def integer_division(dividend: int, divisor: int) -> (int, int):
    """
    Assumes that the dividend and the divisor are positive ints
    Return a tuple containning the quotient and the rest of division
    """
    quotient = dividend // divisor
    rest = dividend % divisor
    
    return(quotient, rest)

quotient, rest = integer_division(10, 3)
# quotient = 3, rest = 1
```
