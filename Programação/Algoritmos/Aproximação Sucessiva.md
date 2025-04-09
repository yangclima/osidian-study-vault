---
tags:
  - Definição
---
É um [[Algoritmo]] que utiliza o [[Teorema de Newton-Raphson]] para resolver problemas que solucionáveis encontrando raízes de polinômios, um código desse tipo pode ser usado para encontrar por exemplo, aproximações precisas para o problema da raiz quadrada.
### Exemplo
```python
epsilon = 0.01
x = 25
guess = x/2

while(abs(guess**2 - x) >= epsilon):
    guess = guess - (((guess**2) - x)/2)

print(f"The square root of {x} is close to {guess}")
```