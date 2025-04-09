Para realizar a clonagem de uma lista podemos usar a feature de fatiação do python da seguinte forma:
```python
copia = lista[:]

# Caso existam elementos mutáveis na lista, é possível usar a função deepcopy
# da biblioteca built-in 'copy'
import copy
copia = copy.deepcody(lista)
```