---
tags:
  - Definição
---
Algo muito discutido nos primórdios da  [[POO e Classes|POO]] foi a ineficiência que pode ser gerada pelo princípio do encapsulamento, para segui-lo, no caso de possuirmos uma lista como atributo, por exemplo, com as ferramentas que dispomos até então precisaríamos criar uma cópia da lista sempre que o `getter` correspondente fosse chamado, a solução para isso são o `generators`  que usam a palavra reservada `yeld` para 'pausar' a execução de uma função retornando um item por vez e mesmo assim possibilitando a iteração sob a lista:
```python
def get_list(self):
    """Return the items in the list one at time"""
    for s in self.list:
        yeld s
```
No exemplo acima o looping rodaria normalmente com o adendo de que, ao chegar no `yeld` a função retornaria o valor atual de `s` e na próxima chamada já retornaria a função do que seria o próximo `yeld`,  a próxima pausa, evitando uma iteração desnecessária sobre a lista para copiá-la.
