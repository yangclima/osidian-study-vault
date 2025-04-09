Os tipos em Python podem ser organizados em dois grupos, os mutáveis e os imutáveis, a grande diferença entre eles é que, os tipos mutáveis são *referências de memória* enquanto os imutáveis são valores por si só, mas afinal, o que isso quer dizer? E como isso pode impactar o nosso código?

Bem, resumidamente, isso significa que os tipos mutáveis podem ser alterados durante a execução do nosso código enquanto os imutáveis não, simplificadamente, podemos entender que ao atribuir um tipo mutável a uma variável não estamos atribuindo um conjunto de bits que representam aquele valor, como se faria com uma string ou um inteiro (Tipos imutáveis), mas sim atribuindo uma endereço de memória o que permite que um mesmo objeto esteja vinculado a mais de uma variável, o que chamamos de [[Aliasing]] e que pode tanto ser útil como também gerar alguns erros, por exemplo:
```python
lista = [1, 2, 3, 4, 5]

for number in lista:
    if number == 2 or number == 3:
        lista.remove(number)

print(lista)
# Out: [1, 3, 4, 5]
```
A primeira vista podemos imaginar que a lista acima teria os elementos `2` e `3` removidos, mas não é bem isso que acontece, a estrutura `for` itera sobre os índices da lista na seguinte ordem:
1. `number = lista[0]`, `number = 1`, `number` não é nem igual a `2` nem igual a `1`
2. `number = lista[1]`, `number = 2`, `number` é  igual a `2`, `lista.remove(2)` 
3. `number = lista[2]`, `number = 4`, `number` não é nem igual a `2` nem igual a `1` (Percebe que o código pula o `3`? Isso acontece por que, como o `2` foi removido, o elemento de índice `2` não é mais o `3` e sim o `4`)
4. `number = lista[3]`, `number = 5`, `number` não é nem igual a `2` nem igual a `1`
5. `number = lista[4]`, `number = null`,  `number` não é nem igual a `2` nem igual a `1`

Percebe o problema que isso pode gerar, para resolver isso, nós copiamos as listas ou qualquer item mutável que seja preciso para que o nosso código funcione bem, através do que chamamos de [[Clonagem]].