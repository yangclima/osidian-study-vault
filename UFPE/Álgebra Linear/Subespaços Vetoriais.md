Um **Subespaço vetorial** do $\mathbb{R}^n$ é um conjunto de vetores $W \subseteq \mathbb{R}^n$ que possui as seguintes propriedades:
1. Contém o vetor nulo, também conhecido como origem do espaço, ou seja, $0 \in W$
2. As combinações lineares de quaisquer vetores pertencentes a $W$ também pertencem a $W$, ou seja, Se $\mathbf{x} \in W$ e $\mathbf{y} \in W$, então, para todos $\lambda_1 \in \mathbb{R}$ e $\lambda_2 \in \mathbb{R}$ vale que: $\lambda_1 \cdot x + \lambda_2 \cdot y \in W$;
# Subespaço vetorial gerado
O subespaço vetorial gerado por $n$ vetores $v_1, v_2, \cdots, v_n$ é o conjunto de todos os vetores que podem ser escritos como combinação linear dos vetores que geram o subespaço, ou seja:
$$
ger[v_1, v_2, \cdots, v_n] = \{\lambda_1v_1 + \lambda_2v_2 + \cdots + \lambda_nv_n: \lambda_1, \lambda_2, \cdots,\lambda_n \in \mathbb{R} \}
$$
# Espaço de linhas
O espaço de linhas de uma [[Matrizes|matriz]] $A$, denotado por $\mathcal{L}(A)$ é o subespaço vetorial gerado pelos vetores $v_1, v_2, \cdots, v_m$ onde cada vetor é uma linha da matriz $A$.
$$
\mathcal{L}(A) = ger[v_1, v_2, \cdots, v_m] = \{x^TA: x \in \mathbb{R}^m\}
$$
# Espaço de colunas
O espaço de colunas de uma [[Matrizes|matriz]] $A$, denotado por $\mathcal{C}(A)$ é o subespaço vetorial gerado pelos vetores $v_1, v_2, \cdots, v_m$ onde cada vetor é uma coluna da matriz $A$.
$$
\mathcal{C}(A) = ger[v_1, v_2, \cdots, v_m] = \{Ax: x \in \mathbb{R}^n\}
$$
Uma observação útil: Um [[Sistemas lineares|sistema linear]] só admite solução se seu vetor-coluna de membros pertence ao espaço coluna de da matriz de coeficientes.  
# Subespaço afim
Um subespaço afim é um subespaço vetorial que não passa pela origem, esse tipo de subespaço pode ser descrito pela translação de um subespaço vetorial $W$ por um vetor $x_0$, ou seja $w^\prime = x_0 + W$. 
# Subespaços como sistemas lineares
Um problema inverso muito comum de ser cobrado é descrever um subespaço vetorial ou subespaço afim através de um sistema linear, isso SEMPRE será possível já que:
- Qualquer subespaço vetorial pode ser descrito como um sistema linear homogêneo, e
- Qual subespaço afim pode ser descrito como um sistema linear não homogêneo
Se um subespaço for dado, por exemplo como o espaço gerado por um conjunto de vetores, podemos juntá-los como colunas de uma matriz e a escalonar obtendo um sistema linear homogêneo a partir do resultado do escalonamento para as linhas nulas de $A$.