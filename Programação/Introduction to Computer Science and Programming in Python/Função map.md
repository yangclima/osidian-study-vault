A função `map` é uma função que recebe com argumento uma função unária `f` e uma lista `L` e retorna uma lista `L1` tal que cada elemento `e` de  `L1` é igual a `f(x)`. De modo mais geral, os argumentos da função `map` são: uma função `f` de `n` argumentos seguida de `n` listas, e retorna um iterador cujos elementos são `f(x1, y1)`:
```python
print(list(map(lambda x, y: x * y, [1, 2, 3], [4, 5])))
# Output: [4, 10]
```