O algoritmo ***merge sort*** é um algortimo básico baseado em divide-and-conquer que se beneficia da facilidade de mesclar (daí é que vem o "merge")  duas listas ordenadas, o que abre portas para separar a lista em várias listas menores e realizar o "merge" dessas, sua complexidade é $O(n \log(n))$, veja:
```python
def merge_sort(L: list) -> list:
    """
    Return a sorted copy of 'L'

    L (list): The list to be sorted
    """
    
    def merge(left: list, right: list) -> list:
        """
        Merges the sorted lists 'left' and 'rigth' and
        return a new sorted list

        left (list): A sorted list
        right (list):A sorted list
        """

        result = []
        i, j = 0, 0

        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                result.append(left[i])
                i += 1
            else:
                result.append(right[j])
                j += 1

        while i < len(left):
            result.append(left[i])
            i += 1

        while j < len(right):
            result.append(right[j])
            j += 1
  
        return result

  

    if len(L) < 2:
        return L[:]
    else:
        mid = len(L) // 2
        left = merge_sort(L[:mid])
        right = merge_sort(L[mid:])
        
        return merge(left, right)
```