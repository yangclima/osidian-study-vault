Além do [[Teorema de Stokes]] e do [[Teorema de Green]], um outro poderoso teorema é o Teorema do Divergente ou Teorema de Gauss, uma vez que este permite o cálculo de [[Integrais de superfície]], mais especificamente integrais de fluxo sobre superfícies fechadas, sem a necessidade de realizar a [[Parametrização de superfícies|parametrização]] dessas superfícies, o teorema enuncia o seguinte:

> Seja $E$ uma região sólida simples e $\mathcal S$ a superfície que delimita $E$, positivamente orientada (Para fora) e seja $\vec F$ um [[Campos vetoriais|um campo vetorial]] cujas componentes possuem [[Derivadas parciais]] contínuas, vale que:
> $$\iint \limits_{\mathcal S} \vec F \cdot d\vec S = \iiint\limits_E (\vec\nabla \cdot \vec F)\,dV$$
> OBS: Lembre-se que $\vec \nabla \cdot \vec F$ é o [[Divergente]] de $\vec F$.

O teorema ainda pode ser estendido para regiões não simples, por exemplo, dada uma região $E$, delimitada por 2 superfícies $\mathcal S_1$ e $\mathcal S_2$ onde $\mathcal S_2$ está dentro de $\mathcal S_1$, como o vetor normal de $E$ será $\hat n_{\mathcal S_1}$ sobre $\mathcal S_1$ e $-\hat n_{\mathcal S_2}$ sobre $\mathcal S_2$, temos:

$$
\iiint\limits_E (\vec\nabla \cdot \vec F)\,dV = \iint \limits_{\mathcal S_1} \vec F \cdot d\vec S - \iint \limits_{\mathcal S_2} \vec F \cdot d\vec S
$$
