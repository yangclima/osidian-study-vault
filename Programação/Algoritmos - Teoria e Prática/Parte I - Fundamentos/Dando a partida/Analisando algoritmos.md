Analisar um [[Algoritmos|algoritmo]] significa prever os recursos que esse algoritmo necessita para executar a sua tarefa. Nesse sentido, múltiplos fatores podem ser relevantes, tais como, largura de banda, memória, ou consumo de energia, no entanto, na maioria dos casos, o principal fator será o tempo de execução.

O grande problema que surge nesse contexto de análise é que há uma série de minúcias associadas a execução de um algoritmo, diferentes instruções e operações podem levar diferentes tempos e ser mais ou menos eficientes, além disso, fatores intrínsecos a execução de um programa, como a linguagem e seu compilador, a arquitetura e modelo do processador, o tipo de memória ou mesmo os outros processos que estão sendo executados simultaneamente no dispositivo consigam alterar o tempo de execução de um algoritmo. Isso tudo leva ao fato de que um mesmo computador, com o mesmo programa e mesma linguagem, possa obter diferentes tempos de execução para uma mesma entrada de dados.

Dessa forma, vemos que é essencial, para analisar um algoritmo, considerar o ambiente em que esse algoritmo será executado, um modelo da tecnologia na qual ele será trabalhado, nesse sentido, na maioria das vezes, utilizaremos o modelo RAM (Random Access Memory) que adota uma série de premissas:

1. Instruções são executadas sequencialmente, uma após a outra
2. Cada instrução básica leva a mesma quantidade de tempo que qualquer outra (Operações aritméticas, movimentação de dados ou controle de fluxo)
3. Cada acesso a um dado leva a mesma quantidade de tempo que qualquer outro acesso
4. Cada word de dados tem um limite no número de bits

Esse modelo é um tanto irreal e ignora vários aspectos importantes da execução de programas em computadores modernos, tais como as diferenças de eficiência entre diferentes operações, a hierarquia de memória e outras áreas obscuras desse modelo, ainda assim, funciona muito bem para antecipar o comportamento de algoritmos em computadores reais e servirá muito bem para a análise de algoritmos na maioria dos casos simplificando muito esse processo. 

Para começar, utilizaremos uma fórmula matemática um tanto complexa para analisar o nosso primeiro algoritmo, a [[Ordenação por inserção]], assumindo que cada linha (Cada linha é um conjunto de operações básicas) é executada em um tempo constante:

```pseudocode
INSERTION-SORT(A, n)
1  for i = 2 to n                     
2    key = A[i]                          
3    j = i - 1                            
    
4    while j > 0 and key < A[j]
5      A[j + 1] = A[j]
6      j = j - 1
      
7    A[j + 1] = key
```

Analisemos então considerando isso e uma entrada de tamanho $n$ para a função:

| Linha | Tempo | Quantidade de execuções   |
| ----- | ----- | ------------------------- |
| 1     | $c_1$ | $n$                       |
| 2     | $c_2$ | $n-1$                     |
| 3     | $c_3$ | $n-1$                     |
| 4     | $c_4$ | $\sum_{i=2}^{n}t_i$       |
| 5     | $c_5$ | $\sum_{i=2}^{n}(t_i - 1)$ |
| 6     | $c_6$ | $\sum_{i=2}^{n}(t_i - 1)$ |
| 7     | $c_7$ | $n - 1$                   |

Nesse contexto, $t_i$ é a quantidade de vezes que a condição do `while` é avaliada para um determinado valor de $i$.

Assim, denotamos o tempo de execução $T(n)$ desse algoritmo como sendo:

$$T(n) = (c_1 + c_2 + c_3 + c_7)n - (c_2 + c_3 + c_7) + c_4\sum_{i=2}^{n}t_i + (c_5 + c_6)\sum_{i=2}^{n}(t_i - 1)$$

Um outro fato interessante é que o tempo de execução dos nossos algoritmos, mesmo nesse contexto simplificado do modelo RAM, pode ainda variar para um tamanho de input $n$ o que justifica que analisemos dois casos de execução, o **melhor caso**, onde o array de entrada já está ordenado e o **pior caso**, onde o array de entrada está ordenado na ordem inversa.

**No melhor caso,** a condição `key < A[j]` já falha na primeira verificação o que significa que nosso $t_i$ será igual a $1$, independente do valor de $i$, o que nos leva a:

$$T(n) = (c_1 + c_2 + c_3 + c_4 + c_7)n - (c_2 + c_3 + c_7 + c_4)$$

Podemos ainda simplificar esse tempo de execução para $T(n) = an + b$ onde $a$ e $b$ são constantes que dependem do tempo de execução de cada linha e então dizer que **no melhor caso**, a ordenação por inserção é uma função linear de $n$.

**No pior caso**, por outro lado, como cada elemento está na posição "oposta" a que deveria, a condição `key < A[j]` nunca falha, exceto quando a variável $j$ esgota (`j > 0` é avaliado como falso) e o nosso $t_i$, portanto, é igual a $i$ e após simplificações (Podemos utilizar a fórmula da soma dos termos de uma PA para avaliar os somatórios) ficamos com:

$$
T(n) = (c_1 + c_2 + c_3 + c_7)n - (c_2 + c_3 + c_4 + c_7) + c_4\dfrac{n(n+1)}{2} + (c_5 + c_6)\dfrac{n(n-1)}{2}
$$

Que, com algumas simplificações, pode ser escrito como $T(n) = an^2 + bn + c$, isto é, no pior caso, o tempo de de execução desse algoritmo é uma função quadrática do tamanho $n$ da sua entrada.

Na maioria dos casos de análise, é justamente no pior caso que estamos interessados, isso por que essa informação nos dá um visão clara sobre o funcionamento do algoritmo, de modo que teremos certeza que o tempo de execução não será maior que $T(n)$ o que é muito importante numa série de aplicações e que não é possível inferir caso olhássemos para o melhor caso ou mesmo para uma caso médio, além disso, para uma ampla gama de casos de uso, o pior caso é relativamente comum, por exemplo, para um algoritmo de busca, o pior caso é quando o valor não existe no conjunto de dados, situação muito comum num [[PostgreSQL|banco de dados]], por exemplo, por fim, o caso médio, mesmo que pareça mais justo, normalmente é quase tão ruim quanto o pior caso. 

Até agora, na análise do nosso algoritmo, utilizamos fórmulas matemáticas, que, no fim das contas, nos dão mais informações do que realmente precisamos sobre a execução, na realidade, as constantes $c_k$ nos fornecem muito pouco sobre a verdadeira eficiência de algoritmo e obscurecem o verdadeiro parâmetro: A taxa ou ordem de crescimento do tempo de execução, também conhecida como complexidade do algoritmo. 

Na realidade, para mensurar essa taxa utilizamos somente o termo dominante da fórmula do seu tempo de execução, deixando de lado a constante que o multiplica e os demais termos, por exemplo, para $T(n) = an^2 + bn + c$ consideraremos somente $n^2$ e para $T(n) = an + b$ consideraremos somente $n$, isso por que o termo dominante é de longe o mais importante para avaliar essa métrica já que é ele que se destaca quando trabalhamos com grandes entradas de dados, muito comuns em aplicações reais.

Para dar destaque a esse termo, introduzimos uma nova notação, ela faz uso da letra grega $\Theta$ (*theta*), popularmente conhecida como Notação Big Theta, por exemplo, dizemos que o algoritmo de Ordenação por Inserção tem um tempo de execução de pior caso de $\Theta(n^2)$ ou que ele tem um tempo de execução de melhor caso de $\Theta (n)$, essa afirmações correspondem respectivamente a dizer que o tempo de execução de pior caso do algoritmo é aproximadamente proporcional a $n^2$ quando $n$ é suficientemente grande e que no melhor caso é aproximadamente proporcional a $n$ quando $n$ é grande.

Em resumo, na maioria das vezes, consideraremos como mais eficiente o algoritmo que tem a menor ordem de crescimento de pior caso, mesmo que para pequenos inputs o algoritmo com maior complexidade possa ser mais rápido, afinal, sempre existirá um limiar $n_0$ tal que para qualquer $n > n_0$ o algoritmo com menor ordem de crescimento seja sempre mais eficiente no pior caso.

# Exercícios
1. Expresse a função $n^3/1000 + 100n^2 - 100n + 3$ em termos da notação $\Theta$

*R:*  $\Theta(n^3)$

2. Considere a ordenação de $n$ números armazenados no arranjo $A[1:n]$ encontrando primeiro o menor elemento de $A[1:n]$ e trocando-o com o elemento em $A[1]$. Em seguida, encontre o menor elemento de $A[2:n]$ e troque-o com $A[2]$. Depois, encontre o menor elemento de $A[3:n]$ e troque-o com $A[3]$. Continue desta maneira para os primeiros $n - 1$ elementos de $A$. Escreva o pseudocódigo para este algoritmo, que é conhecido como **ordenação por seleção** (_selection sort_). Qual invariante de laço este algoritmo mantém? Por que ele precisa ser executado apenas para os primeiros $n - 1$ elementos, em vez de para todos os $n$ elementos? Dê o tempo de execução no pior caso da ordenação por seleção na notação $\Theta$. O tempo de execução no melhor caso é melhor?

*R*:

```pseudocode
SELECTION-SORT(A, n)
  for i = 1 to (n - 1)
    smallest_index = i
  
    for j = i + 1 to n
      if A[j] < A[smallest_index]
        smallest_index = j
        
    if (smallest_index != i)
      temp = A[i]
      A[i] = A[smallest_index]   
      A[smallest_index] = temp
```

```ts
function selectionSort(arr: number[]): void {
  for (let i = 0; i < arr.length - 1; i++) {
    let smallest_index = i;

    for (let j = i + 1; j < arr.length; j++) {
      if (arr[j] < arr[smallest_index]) {
        smallest_index = j;
      }
    }

    if (smallest_index !== i) {
      let temp = arr[i];
      arr[i] = arr[smallest_index];
      arr[smallest_index] = temp;
    }
  }
}
```

Uma invariante possível para esse algoritmo é:

**Invariante:** "Os $i -1$ primeiros valores do Array estão sempre ordenados e são constituídos pelo $i-1$ menores números do conjunto de entrada" 
**Inicialização:** Como o valor inicial de $i$ é $1$, então, de fato, os $i-1=0$ valores do Array são ordenados (Um conjunto vazio é um conjunto ordenado) e constituídos pelos $i-1=0$ menores valores do conjunto de entrada
**Manutenção:** A cada iteração, analisamos através de uma busca linear o menor número no conjunto $A[i:n]$ e o trocamos de lugar com o $A[i]$, desse modo, a cada iteração, encontramos o $i$-ésimo menor número do conjunto de entrada e o movemos para a posição $i$, de modo que ao fim da iteração, o subconjunto $A[1:i]$ é formado pelos $i$ menores números do input, ordenados do menor para o maior, ao incrementar $i$, temos então que é verdadeiro no início da próxima iteração que os $i - 1$ primeiros valores do array são o conjunto ordenado dos $i-1$ menores valores da entrada, confirmando a invariante.
**Término:** Sabemos que a execução termina com $i = n$ (Após o último incremento, para o qual falha a verificação da condição do laço), sabe-se então que , pela invariante, os $n - 1$ primeiros valores do array estão ordenados e constituem os $n - 1$ menores valores da entrada, por consequência, sabemos que o $n$-ésimo valor do Array é o elemento que restou, ou seja, o maior valor do conjunto de entrada e está na última posição do array ordenado, o que nos leva a concluir que, de fato, o algoritmo ordena a lista corretamente.

Como bem descreve a análise de término da invariante, o algoritmo precisa executar para os $n -1$ elementos ao invés dos $n$ por que ao identificar os $n - 1$ menores elementos do conjunto se tem, por consequência, que o elemento que sobrou deve logicamente ser o maior elemento.

Quanto a complexidade, o `for` mais externo executa $n - 1$ vezes, vezes para as quais o Loop interno executa, $n - 1$, $n-2$, $n-3$, e assim por diante até $1$, utilizando a fórmula da soma dos termos de uma PA obteremos que esse loop interno executa $n(n-1)/2$ vezes e portanto a complexidade dele é $\Theta (n^2)$.

No melhor caso, só teremos diferença se considerarmos o último `if`, que falhará e por isso o Swap as variáveis não será executado isso entretanto adiciona apenas um fator constante $-(n -1)$ na função teórica para o tempo de execução da variável e não muda a sua complexidade, que continuaria $\Theta(n^2)$.

3. Considere novamente a busca linear (veja o Exercício 2.1-4). Quantos elementos do arranjo de entrada precisam ser verificados em média, assumindo que o elemento procurado tem a mesma probabilidade de ser qualquer elemento no arranjo? E no pior caso? Usando a notação $\Theta$, dê os tempos de execução no caso médio e no pior caso da busca linear. Justifique suas respostas.

*R:*

Considerando que o elemento procurado tem a mesma probabilidade de ser qualquer elemento do arranjo, o que nos leva a assumir que o elemento buscado está presente no conjunto, cada elemento tem uma probabilidade de $1/n$ de ser o correto, para encontrar o caso médio, podemos usar então a [[Esperança]] ou **Valor esperado**, um conceito estatístico que representa o valor médio esperado numa sequência de experimentos independentes, nesse caso, nosso evento alvo, ou [[Variável Aleatória Discreta|Variável aleatória]] é $X_i$ que nesse caso representa encontrar o valor buscado na $i$-ésimo consulta, temos então:

$$E[X] = 1\left(\dfrac{1}{n}\right) + 2\left(\dfrac{1}{n}\right) + \cdots +  n\left(\dfrac{1}{n}\right) = \dfrac{1}{n}\cdot \dfrac{n(n+1)}{2} = \dfrac{n+1}{2}$$

Dessa forma, em média, encontraremos o valor buscado na tentativa de número $(n+1)/2$, o que representa uma complexidade $\Theta (n)$ no caso médio, no pior caso, por outro lado, consultaremos todos os $n$ elementos do conjunto, obtendo também uma complexidade $\Theta (n)$.

4. Como você pode modificar qualquer algoritmo de ordenação para obter um bom tempo de execução no melhor caso?

Eu posso adicionar uma etapa inicial que verifica se o conjunto de entrada está ordenado previamente, o que, no melhor caso, reduz a complexidade para a complexidade linear, isto é, $\Theta (n)$. 