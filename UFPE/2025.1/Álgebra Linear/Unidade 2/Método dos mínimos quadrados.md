Dado um [[Sistemas lineares|Sistema linear]] $S$ sem solução $Ax = b$, um vetor $x$ que minimiza a distância $||Ax - b||$ é dito uma **Solução de mínimos quadrados** de $S$, o que pode ser encontrado utilizando-se a [[Bases ortogonais|projeção ortogonal]] do vetor $b$ sobre o [[Espaços vetoriais|espaço de colunas]] de $A$, ou seja:
$$
x \text{ é solução de M.Q.} \iff Ax = b_0 = Proj_{\mathcal{C}(A)}(b)
$$
Dentre os vetores que satisfazem essa condição, nos interessa o vetor que tem norma mínima, encontrado pela interceptação do [[Complemento ortogonal]] do espaço de colunas de $A$
