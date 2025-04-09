Uma lista é um objeto Python que se encaixa no grupo de tipos estruturados de dados e que  consiste numa sequência ordenada de elementos de qualquer tipo. Um tupla pode ser escrita como literal através de elementos separados por virgula dentro de colchetes:
```python
lista = [1, 'a', ['b', 'c'], (1, 'e'), 4.0]
```
Como é possível notar, as listas são muito parecidas com as [[Tuplas e Atribuição Múltipla|tuplas]], inclusive suportam as mesmas operações que esta, ou seja, podemos indexar, concatenar ou fatiar as listas:
```python
index = ['a', 'b', 'c', 'd'][2]
# Out: 'c'

repet = ['a'] * 3
# Out: ['a', 'a', 'a']

concat = ['a', 'b'] + ['c', 'd']
# Out: ['a', 'b', 'c', 'd']

slic = ['a', 'b', 'c', 'd'][1:4]
# Out: ['b', 'c', 'd']
```
A grande diferença entre listas e tuplas está relacionada aos conceitos [[Mutabilidade e Imutabilidade]], relacionados com algo chamado [[Aliasing]] que pode gerar alguns problemas na execução de problemas que usam listas e que pode ser corrigido com a [[Clonagem]]. Alguns métodos úteis para utilizar as listas em seus programas são:

| **Função**          | **Ação **                                               |
| ------------------- | ------------------------------------------------------- |
| `lista.append(e)`   | Adiciona o elemento `e` no fim da lista                 |
| `lista.count(e)`    | Retorna o número de vezes que `e` aparece na lista      |
| `lista.insert(i,e)` | Insere o elemento `e` no índice `i` da lista            |
| `lista.extend(L1)`  | Adiciona os elementos da lista `L1` no fim da lista     |
| `lista.remove(e)`   | Remove a primeira ocorrência de `e` na lista            |
| `lista.index(e)`    | Retorna o índice da primeira ocorrência de `e` na lista |
| `lista.pop(i)`      | Remove o elemento de índice `i` e o retorna             |
| `list.sort()`       | Organiza os itens da lista em ordem crescente           |
| `list.reverse()`    | Inverte a ordem dos elementos da Lista                  |
