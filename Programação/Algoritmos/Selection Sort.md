O algoritmo ***selection sort*** é um [[Algoritmo|algoritmo]] básico baseado no princípio de divide-and-conquer que consiste na classificação de uma lista por meio da análise consecutiva de seus elementos procurando sempre o menor item de uma lista e o-separando até que a lista esteja organizada. Sua complexidade é $O(n^2)$.
```python
def selection_sort(L: list) -> None:
	"""
    Sort the list 'L' in ascending order and return None

    L (list): The list to be sorted
    """
    suffix_start = 0
    while suffix_start != len(L):
        for i in range(suffix_start, len(L)):
            if L[i] < L[suffix_start]:
                L[suffix_start], L[i] = L[i], L[suffix_start]
                
        suffix_start += 1
```