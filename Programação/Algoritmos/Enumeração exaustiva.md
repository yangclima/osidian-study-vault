---
tags:
  - Definição
---
Um dos [[Algoritmo|algoritmos]] mais simples, fácil de criar, de entender e de testar. Consiste basicamente em testar possibilidades até que a resposta correta seja encontrada ou até que se esgote o espaço de possibilidades.
### Exemplo:
No exemplo utilizamos a enumeração exaustiva para encontrar a raiz cúbica de números que são cubos perfeitos.
```python
x = 25
epsilon = 0.01
step = epsilon**2

num_guesses = 0
ans = 0.0

while(abs(x - ans**2) >= epsilon and ans <= ans):
    ans += step
    num_guesses += 1

print(f"num_guesses = {num_guesses}")
if(abs(x - ans**2) >= epsilon):
    print(f"Failed on find of square root of {x}")
else:
    print(f"{ans} is close to square root of {x}")
```

