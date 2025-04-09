---
tags:
  - Definição
---
A [[Enumeração exaustiva]], mesmo com toda a capacidade computacional que temos, rapidamente se torna inviável, pois o número de tentativas que precisamos fazer para encontrar uma resposta cresce rapidamente, dessa forma surge como  alternativa a **pesquisa binária**, um  [[Algoritmo]] que se assemelha  a procurar uma palavra no dicionário, não vamos folheando página por página, se procuramos uma palavra com __m__  por exemplo, tentamos abrir o dicionário no meio e podemos ir estimando o lugar da próxima página que pode nos interessar até encontrar a palavra somente vendo de a primeira palavra da página atual está antes ou depois da que procuramos.
### Exemplo
```python
x = 25
epsilon = 0.01
num_guesses = 0

# Limites - Definimos o nosso espaço de possibilidades
low = 0.0
righ = max(1.0, x)

# Palpite - Pegamos o número central do nosso espaço como palpite inicial
ans = (low + right) / 2

while(abs(x-ans**2) >= epsilon):
    num_guesses += 1
    # Se o palpite for maior do que o que procuramos, pegamos o intervalo
    # inferior, ou seja [low, high] se torna [low, ans]
    if(ans**2 > x):
        high = ans
    # Caso contrário, pegamos o intervalo superior, ou seja,
    # [low, high] se torna [ans, high]
    else:
        low = ans

	# Defrinimos o novo palpite como o centro do novo intervalo
	ans = (low + right) / 2

if(abs(x - ans**2) >= epsilon):
    print(f"Failed on find of square root of {x}")
else:
    print(f"{ans} is close to square root of {x}")
```

