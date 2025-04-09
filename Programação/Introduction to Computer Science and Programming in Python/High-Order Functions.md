Funções High-Order são funções capazes de receber outras funções como argumento e que utilizam destas para sua execução, um exemplo que poderia ser construído é: 
```python
def apply_to_each(L: list, f: callable) -> list:
    """
    Mutates L by replacing each element, e, of L by f(e).
    """

    for i in range(len(L)):

        L[i] = f(L[i])


def square(x: float) -> float:
	"""
    Returns the square of x.
    """
    return x * x


lista = [1, -2, 3.33]

apply_to_each(lista, square)

print(lista)
# Out: [1, 4, 11.0889]
```
O python tem uma função built-in que possui o mesmo objetivo da função acima, a função [[Função map|map]].