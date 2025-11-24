Na estatística/probabilidade, estamos interessados, na grande maioria das vezes em contar os elementos de um [[Conjuntos e Notações|conjunto]] de interesse ou de uma parte limitada de um conjunto, nesse sentido, dois princípios de contagem muito úteis são o **Princípio da Inclusão-Exclusão** e a **Regra do Produto**.

O princípio da Inclusão-Exclusão permite obter o número de elementos da união de dois conjuntos, o que a princípio parece estranho, afinal não seria só somar o número de elementos de $A$ e o número de elementos de $B$? Na verdade não, isso só funciona se não houver elementos na intersecção de $A$ e $B$ já que a união não pode incluir duas vezes esses elementos, vale então o seguinte:

$$
|A \cup B| = |A| + |B| - |A \cap B|
$$

A regra do produto, por sua vez, nos diz o seguinte: Se temos $m$ formas de performar uma ação $u$ e então $n$ formas de performar uma ação $v$, então, temos $m\cdot n$ formas de performar a ação $u$ seguida da ação $v$, o mesmo pode ser estendido para um número maior de ações.