Uma [[Bases|base]] ortogonal é uma base para um [[Produto interno|espaço vetorial Euclidiano]] que também é um conjunto ortogonal, ou seja, um conjunto no qual todos os vetores são ortogonais entre si, ou seja, tomados quaisquer dois vetores $v_1$ e $v_2$ da base, $\langle u, v\rangle = 0$, se, além disso, os vetores forem unitários, a base é dita, **ortonormal**.

A projeção ortogonal de um vetor $v$ sobre o eixo gerado por outro vetor não nulo $u$ é o vetor:
$$
Proj_u (v) = \dfrac{\langle u,v \rangle}{\langle u, u\rangle}u
$$
De tal forma que $u  \perp v - Proj_u (v)$. Também é possível definir a projeção ortogonal de um vetor sobre um [[Subespaços Vetoriais|Subespaço vetorial]]: Dado um subespaço qualquer $W$ e $\mathcal{B} = \{v_1, v_2, \cdots, v_n\}$ uma base **ortogonal**  qualquer de $W$, temos:
$$
Proj_W(u) = Proj_{v_1}(u) + Proj_{v_2}(u) + \cdots + Proj_{v_n}(u)
$$