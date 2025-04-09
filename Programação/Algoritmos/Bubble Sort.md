O algoritmo buble sort é utiliza da repetição comparações de pares de valores consecutivos em uma lista, trocando os valores de lugar caso o primeiro seja maior que o segundo até que os maiores valores "flutuem" até o topo da lista, ese algoritmo possui complexidade $O(n^2)$:
```python
def bubble_sort(L: list):
    """
    Sort the list 'L' in ascending order and return None

    L (list): The list to be sorted
    """
    top = len(L)

    while top != 0:
        for i in range(0, top - 1):
            if L[i] > L[i+1]:
                L[i], L[i+1] = L[i+1], L[i]
                
        top -= 1
```
