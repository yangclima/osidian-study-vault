---
tags:
  - Procedimento
---
O **HtDF** é um método de design, uma espécie de receita que pode ser utilizada para tornar problemas difíceis mais fáceis bem como tornar problemas mal formulados em soluções bem definidas, resumindo a construção de qualquer função nos seguintes passos:
1. Escreva a assinatura da função, seu propósito em uma linha e o seu rascunho (stub)
2. Crie exemplos e testes que mostram como a função deve se comportar
3. Faça inventário, cheque como você precisará utilizar os parâmetros para cumprir o propósito da função e se necessário crie um template que te ajude a organizar as ideias
4. Escreva o corpo da função
5. Teste e caso haja algum problema debugue seu código

```python
# Passo 1:
def square(n: int) -> int:
    """Receives a number 'n' and returns its square"""
    return 0

# Passo 2: 

# Example1: square(1) -> 2
# Example2: square(-2) -> -4
# Example3: square(0) -> 0

def test_square() -> None:
    """Unit tests for the function 'square'"""
    assert square(1) == 2

	assert square(4) == -4

	assert square(0) == 0

# Passo 3:
def square(n: int) -> int:
    """Receives a number 'n' and returns its square"""
    return ... n

# Passo 4:
def square(n: int) -> int:
    """Receives a number 'n' and returns its square"""
    return n * 2
```