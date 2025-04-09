Um dict é um tipo estruturado de dados, assim como [[Listas]]  e  [[Tuplas e Atribuição Múltipla|Tuplas]] em Python que armazena pares de chave-valor, onde a chave pertence a qualquer tipo imutável e o valor pertence a qualquer tipo. Como literal, o dict pode ser escrito como uma sequência de elementos separados por vírgulas entre chaves onde cada elemento configura um par chave-valor os quais são separados por 'dois-pontos':
```python
dct = {1: 'a', (1,2): 'hello', "World": 1}
```
Diferente de outros tipos estruturados, os dicts não tem suporte para concatenação através do sinal de soma, nem fatiação, nem repetição. A indexação, por sua vez ocorre por meio das chaves dos pares:
```python
dct = {1: 'a', (1,2): 'hello', "World": 1}

print(dct['World'])
# Out: 1
```