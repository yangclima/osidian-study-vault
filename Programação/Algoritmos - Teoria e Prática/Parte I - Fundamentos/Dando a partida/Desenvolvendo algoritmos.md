
```pseudocode
MERGE(A, p, q, r)
  
```


# Exercícios

1. Usando a figura 2.4 como modelo, ilustre a operação do algoritmo de ordenação por intercalação num array contendo inicialmente a sequência $\langle 3,41,52,26,38,57,9,49\rangle$.

![[alg_002.png]]

2. A condição na primeira linha da procedure `MERGE-SORT` verifica $p \geq r$ ao invés de $p \neq r$. Se essa função for chamada com $p> r$, sabemos que o subconjunto $A[p:r]$ é vazio. Argumente que, desde que a chamada inicial desse procedure `MERGE-SORT(A,1,n)` seja chamada incialmente com $n\geq 1$, testar se $p\neq r$ é suficiente para garantir que não haverão chamadas recursivas com $p>r$.

Queremos provar que a condição $p \neq r$ como condição para o prosseguimento da recursão garante que não haverá chamadas recursivas com $p > r$ desde que na chamada inicial tenhamos $p = 1$ e $r \geq 1$. Essa hipótese é verdadeira, se e somente se, a afirmação de que os índices $p$ e $r$ ao longo da execução do algoritmo satisfazem $p \leq r$ for uma invariante. 

Para provar que a invariante proposta é válida, analisemos a sua inicialização e manutenção.

Quanto a inicialização, como restringimos a chamada inicial à condição de que $n = r \geq 1$ e $p = 1$ sabemos então que a condição da invariante é inicialmente verdadeira.

Analisando agora a manutenção, pelo invariante (Partindo da premissa de que a inicialização do invariante é válida e cada iteração inicia-se com a afirmação $p \leq r$ verdadeira) sabemos que $p \leq r$ e que a execução só prossegue se $p \neq r$, nesse caso, o valor $q$, dado por $q = \lfloor (p+r)/2 \rfloor$ garante matematicamente que $p\leq q < r$, assim, avaliemos as chamadas recursivas:

- Na chamada `MERGE-SORT(A, p, q)`, como $p\leq q$ e os novos parâmetros são $p_{novo} = p$ e $r_{novo} = q$ sabemos que $p_{novo} \leq r_{novo}$ e a invariante se mantém.
- Na chamada `MERGE-SORT(A, q+1, r)`, como $q < r$ e os novos parâmetros são $p_{novo} = q+1$ e $r_{novo} = r$ temos que, sendo $q$ e $r$ inteiros, $q+1 \leq r$ e portanto, $p_{novo} \leq r_{novo}$ de modo que a invariante se comprova.

Se é verdade que $p\leq r$ é uma invariante, conclui-se então que, caso a condição do if, restrinja que $p \neq r$, teremos sempre $p < r$ e portanto, nenhuma chamada recursiva com $p> r$.

4. Utilize a indução matemática para mostrar que quando $n\geq 2$ é uma potência exata de $2$, a solução da recorrência $$T(n) = \begin{cases}2; & \ \ \ \text{se } \ \ n =  2 \\ 2T(n/2) + n; & \ \ \ \text{se } \ \ n >  2\end{cases}$$ É $T(n) = n\log_2{(n)}$.



Analisando o caso base, sabemos que 
