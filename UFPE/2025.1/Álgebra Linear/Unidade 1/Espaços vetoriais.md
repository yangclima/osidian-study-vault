Um Grupo Abeliano é um conjunto $V$ no qual está definida uma operação binária (Normalmente denotada por $u + v$), com relação a qual o conjunto é fechado (Ou seja $u,v \in V \implies (u + v) \in V$) e que satisfaz as seguintes propriedades:
1. Associatividade: $u + (v + w) = (u + v) + w$
2. Comutatividade: $u + v = v + u$
3. Neutro aditivo: $\exists \ v_0 \in V : u + v_0 = u$
4. inverso aditivo: $\forall \ u \in V, \exists \ -u \in V : u + (-u) = v_0$
Um Grupo Abeliano $(V, +)$ para o qual também está definida uma operação em $\mathbb{R}$ denotada por $\lambda v, (v \in V, \lambda \in \mathbb{R})$ com relação a qual o conjunto $V$ é fechado e que possui as seguinte propriedades:
5. Distributividade da soma de escalares: $(\lambda_1 + \lambda_2)v = \lambda_1 v + \lambda_2 v$ 
6. Distributividade sobre a soma de vetores: $\lambda(v_1 + v_2) = \lambda v_1 + \lambda v_2$
7. Associatividade: $\lambda_1 (\lambda_2 v) = (\lambda_1 \lambda_2) v$
8. Neutro multiplicativo: $\exists 1 \in \mathbb{R} : 1v = v$
Ou seja, o conjunto $V$ e as duas operações definidas sobre ele em conjunto são chamados de Espaço Vetorial, além disso, qualquer subconjunto de $V$ que possui $v_0$ e é fechado para as operações é chamado de [[Subespaços Vetoriais|Subespaço vetorial]] de $V$.
# Combinações lineares
Num espaço vetorial, uma soma do tipo $\lambda_1 v_1 + \lambda_2 v_2 + \cdots + \lambda_k v_k$ onde $v_1, v_2, \cdots, v_k \in V$ é denominada combinação linear dos vetores $v_1, v_2, \cdots, v_k$ 
# Translação por um vetor
Dado um subconjunto $C$ de $V$, a translação desse subconjunto por um vetor $u \in V$ é o novo conjunto definido por:
$$
u + C = \left\{ u + v : v \in C \right\}
$$
# Subespaço vetorial gerado
Dado um espaço vetorial $V$, um subespaço vetorial gerado pelos vetores $v_1, v_2, \cdots v_k$ pertencentes a $V$ denotado por $ger[v_1, v_2, \cdots v_k]$ é o subconjunto que engloba todas as combinações lineares dos vetores geradores.
# Subespaço vetorial afim
Um subespaço vetorial afim é um subespaço vetorial de $V$ translado por um vetor qualquer $u \in V$, no caso do vetor já pertencer ao subespaço, a translação continua sendo subespaço, caso o contrário, a não inclusão do vetor nulo configura que a translação não é um subespaço. 