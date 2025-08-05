A ortogonalização de Grand-Schmidt é um processo utilizado para obter um [[Produto interno|conjunto ortogonal de vetores]] a partir de um conjunto L.I. qualquer de vetores, processo que consiste em, dado um conjunto de vetores L.I. (Uma [[Bases|base]]) $\{v_1, v_2, \cdots, v_k, v_{k+1}\}$:
$$
\begin{aligned}
& w_1 = v_1 \\
& w_2 = v_{2} - Proj_{w_1}(v_{2}) \\
& w_{k+1} = v_{k+1} - Proj_{w_k}(v_{k+1}) 
\end{aligned}
$$

De forma que no final obtemos um conjunto ortogonal que serve como uma [[Bases ortogonais|base ortogonal]] para o espaço gerado pelos vetores $v_1, v_2, \cdots, v_k, v_{k+1}$.
