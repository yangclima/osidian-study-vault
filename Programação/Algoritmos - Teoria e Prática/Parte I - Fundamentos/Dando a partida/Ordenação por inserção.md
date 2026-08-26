O primeiro [[Algoritmos|algoritmo]] que veremos é chamado de **Algoritmo de Ordenação por Inserção** ou simplesmente *Insertion Sort*, esse algoritmo se assemelha ao procedimento que seguimos para, por exemplo, ordenar um baralho de cartas na ordem:

Com a pilha de cartas sobre a mesa, pegamos a carta superior do baralho e colocamos na mão esquerda, em seguida, com a mão direita, pegamos mais uma carta da pilha e comparamos seu número com a carta que já está na mão esquerda, se o seu número for menor que o dela, a colocamos à esquerda da primeira carta, caso contrário, à direita. e
Em seguida, repetimos:  pegamos um carta na pilha e a comparamos carta a carta, do final da lista de cartas na mão esquerda até seu início ou até encontrar uma carta cujo número é menor que o da que acabamos de pegar, caso em que colocaremos a nova carta à sua direita.

Note então que na nossa mão esquerda teremos uma lista sempre ordenada que é uma sub lista da lista que está sendo ordenada e que o algoritmo consiste na repetição sequencial de um mesmo passo, pegar um carta, compará-la com as cartas do sub array até achar uma carta menor e então inserir a carta nessa posição.

Um exemplo de implementação desse algoritmo:

```Pseudocode
INSERTION-SORT(A, n)
  for i = 2 to n
    key = A[i]
    j = i - 1
    
    while j > 0 and key < A[j]
      A[j + 1] = A[j]
      j = j - 1
      
    A[j + 1] = key
```

```ts
function insertionSort(arr: number[]): {
  for (let i = 1; i < arr.length; i++) {
    let key = arr[i];
    let j = i - 1;
  
    while (j >= 0 && key < arr[j]) {
      arr[j + 1] = arr[j];
      j = j - 1;
    }

    arr[j + 1] = key;
  }
}
```

Visualmente, essa ordenação se dá da  seguinte forma:

![[alg_001.png]]

Analisar esse algoritmo nos leva a um novo conceito muito útil para verificar a validade da saída de um procedimento como esse, as **Invariantes de Laço**. Uma invariante de laço ou *Loop Invariant* é nada mais que uma condição ou propriedade que permanece válida antes e depois de um laço de repetição, nesse sentido, para que uma condição seja considerada uma invariante de laço precisamos mostrar que ela satisfaz:

1. Inicialização: Antes da execução do laço a propriedade ou condição é verdadeira
2. Manutenção: A cada iteração do laço a propriedade ou condição se mantém verdadeira
3. Término: Ao fim da iteração, a invariante, ainda válida, nos fornece uma propriedade útil que nos ajuda a mostrar que o algoritmo resolve corretamente o problema

No caso do Insertion Sort, a invariante poderia ser:

> A cada iteração do laço o sub array  `arr[0:i-1]` consiste nos elementos originais de `arr[0:i-1`, porém, corretamente ordenados  

E mostramos:

1. Inicialização: Como o valor inicial de $i$ é $1$ e, portanto, $i-1 = 0$, de fato, o sub array composto apenas pelo primeiro elemento (`arr[0]`) contém os elementos originais de `arr[0:0]` corretamente ordenados (Um array de 1 único valor está ordenado)
2. Manutenção: A cada iteração do for loop o que é feito é inserir o elemento da posição `i` na posição correta no sub array por meio de um deslocamento desse elemento para esquerda até encontrar a posição certa para ele, por isso, de fato, a invariante é mantida a cada iteração
3. Término: Dadas as conclusões da inicialização e da manutenção, como a iteração começa com `i = 1` e termina com `i = array.length - 1`, justamente o último índice do array, por isso, chegamos a conclusão de que o algoritmo ordena de fato o array

# Exercícios
1. Usando a figura 2.2 como modelo, ilustre a operação do `Insertion-Sort` num  array contendo inicialmente a sequência $\langle 31; 41; 59; 26; 41; 58\rangle$

*R: Ver [[alg_001.png]]*  

2. Considere a função SUM-ARRAY. Ela calcula a soma dos $n$ números no array `A[1:n]`. Estabeleça uma invariante de laço para esse procedure e utilize sua inicialização,  manutenção e término para mostrar que ele retorna a soma dos números em `A[1:n]`. 

*R: A invariante pode ser: "A cada iteração a variável `sum` equivale a soma dos `i - 1` primeiros números do array",  quanto a inicialização, como `sum` começa com o valor $0$ e `i` começa com o valor $1$, sabemos que, de fato, `sum` inicialmente equivale a soma dos 0 primeiros número do array, em seguida, quanto a manutenção, como a cada iteração o que o algoritmo faz é somar o valor na posição `i` ao valor anterior de `sum`, de fato a invariante se mantém durante a iteração e por fim, como a execução termina quando `i = n` e `n` é o último índice do array, de fato, todos os valores passam pela iteração e portanto o algoritmo realmente retorna a soma de todos os seus itens.*

3. Reescreva o procedimento INSERTION-SORT para ordenar em ordem monotonicamente decrescente, em vez de monotonicamente crescente.

*R:* 

```
INVERSE-INSERTION-SORT(A, n)
  for i = 2 to n
    key = A[i]
    j = i - 1
    
    while j > 0 and key > A[j]
      A[j + 1] = A[j]
      j = j - 1
      
    A[j + 1] = key
```

```ts
function inverseInsertionSort(arr: number[]): {
  for (let i = 1; i < arr.length; i++) {
    let key = arr[i];
    let j = i - 1;
  
    while (j >= 0 && key > arr[j]) {
      arr[j + 1] = arr[j];
      j = j - 1;
    }

    arr[j + 1] = key;
  }
}
```

4. Considere o problema de busca:

> **Input:** Uma sequência de $n$ números $\langle a_1, a_2, \cdots, a_n \rangle$ e um valor $x$

> **Output:** Um índice $i$ tal que $x$ é igual $A[i]$ ou o valor especial `NIL` se $x$ não aparece no array

Escreva o pseudocódigo para linear search, que busca por $x$ no array do início ao fim. Prove que seu algoritmos está correto usando uma invariante e garanta que essa invariantes respeita as 3 condições.

*R:* 

```pseudocode
LINEAR-SEARCH(A, n, x) 
  index = NIL
  i = 1
  
  while i <= n and index == NIL
    if A[i] = x
      index = i
    i = i + 1
      
  return index
```

```ts
function linearSearch(arr: number[], x: number): number | null {
  let index = null;
  let i = 0;

  while (i < arr.length && index === null) {
    if (arr[i] === x) {
      index = i;
    }
  }

  return index;
}
```

Invariante: "A variável ``index`` tem o valor do índice no qual o valor `x` está armazenado nos primeiros `i - 1` elementos de `A` ou caso esse índice não exista NIL", 

Inicialização: como, com certeza, não existe um índice do array que armazena $x$ nos primeiros $i - 1$ elementos de `A`, afinal, como i começa com o valor $1$, $i - 1 = 0$, a validade é garantida na inicialização

Manutenção: a cada iteração é verificado se o elemento na posição `i` é igual a `x`, caso seja, a condição se mantém verdadeira já que o valor de ``index`` passará a representar o índice que armazena o valor igual  a `x` e `i` será incrementado, de modo que de fato, ``index`` equivale ao valor da posição que armazena um valor igual a `x` nos primeiros $i - 1$ elementos caso contrário continuará NIL já que tal elemento não existe nos primeiros $i - 1$ elementos e a condição ainda assim é verdadeira 

Término: A execução termina ao varrer todos os elementos de `A` ou ao encontrar um índice de `A` cujo valor é igual a `x`, no primeiro caso, o valor final de `i` é $n + 1$ e o valor `index` é NIL o que satisfaz a invariante já que nesse caso confirma-se que não existe elemento de valor igual a `x` nos $i - 1 = n$ primeiros elementos (Não existe tal elemento no array), no outro caso, quando um valor igual a `x` é encontrado, `i` ainda é incrementado uma última vez e portanto, de fato, `index` representa o índice do array cujo valor associado é igual a `x` nos $i - 1$ primeiros elementos


5. Considere o problema de somar dois inteiros binários $a$ e $b$ de $n$ bits, armazenados em dois arrays de $n$ elementos $A[0:n - 1]$ e $B[0:n - 1]$, onde cada elemento é $0$ ou $1$, $a = \sum_{i=0}^{n-1} A[i] \cdot 2^i$ e $b = \sum_{i=0}^{n-1} B[i] \cdot 2^i$. A soma $c = a + b$ dos dois inteiros deve ser armazenada em formato binário em um array de $(n + 1)$ elementos $C[0 \dots n]$, onde $c = \sum_{i=0}^{n} C[i] \cdot 2^i$. Escreva um procedimento `ADD-BINARY-INTEGERS` que receba como entrada os arrays $A$ e $B$, juntamente com o comprimento $n$, e retorne o array $C$ contendo a soma.

```pseudocode
ADD-BINARY-INTEGERS(A, B, n)
  carry = 0
  C = []

  for i = 0 to n - 1:
    sum = A[i] + B[i] + carry
    if sum > 1
      C[i] = sum - 2
      carry = 1
    else
      C[i] = sum
      carry = 0
      
  C[n] = carry
  return C
```

```ts
function addBinaryIntegers(a: (0 | 1)[], b: (0 | 1)[]): (0 | 1)[] {
  let carry: 0 | 1 = 0;
  const c: (0 | 1)[] = [];

  for (let i = 0; i < a.length; i++) {
    let sum = carry + a[i] + b[i];

    if (sum > 1) {
      c[i] = (sum - 2) as 0 | 1;
      carry = 1;
    } else {
      c[i] = (a[i] + b[i] + carry) as 0 | 1;
      carry = 0;
    }
  }
  
  c[a.length] = carry;

  return c;
}
```