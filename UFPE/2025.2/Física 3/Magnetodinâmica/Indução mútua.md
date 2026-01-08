Suponha duas bobinas colocadas numa região próxima uma da outra, a primeira tem $N$ espiras e carrega uma corrente $I_1$, o que dá origem a um [[Campo Magnético]] $\vec B_1$ e a segunda onde, devido a proximidade com a primeira bobina algumas linhas de campo a atravessam.

Seja então $\Phi_{12}$ o fluxo magnético através de uma espira da segunda bobina, fazendo com que a corrente $I_1$ varie no tempo o campo magnético $\vec B_1$ deve também variar fazendo por consequência o fluxo magnético $\Phi_{12}$ apresentar uma variação no tempo, [[Lei de Faraday|induzindo]] então uma [[Força eletromotriz]] $\varepsilon_{12}$ na segunda bobina:

$$
\varepsilon_{12} = -N\cdot\dfrac{d\Phi_{12}}{dt} = -N\cdot\dfrac{d}{dt}\iint\vec B_1 \cdot d\vec A
$$

A derivada temporal do [[Fluxo magnético]] $\Phi_{12}$ na segunda bobina é então proporcional a derivada temporal da corrente na primeira bobina, por uma constante de proporcionalidade $M_{12}$:

$$
N\cdot\dfrac{d\Phi_{12}}{dt} = M_{12}\dfrac{dI_1}{dt}
$$

Onde $M_{12}$ é denominada **indutância mútua** e pode também ser escrita da seguinte maneira:

$$
M_{12} = \dfrac{N_2 \Phi_{12}}{I_1}
$$

Essa constante depende apenas das características geométricas da bobina, tais como raio e o número de espiras das bobinas.

A unidade no sistema internacional para a indutância é o "Henry" ($H$), ou seja:

$$
Und \ M = [H] = 1 \ T \cdot m^2 \cdot A^{-1}
$$

Perceba que, da mesma maneira que uma corrente na primeira bobina induz uma corrente na segunda, uma corrente na segunda deve induzir uma corrente na primeira bobina, nesse caso:

$$
M_{12} = M_{21} = M = \dfrac{N_2 \Phi_{12}}{I_1} = \dfrac{N_1 \Phi_{21}}{I_2}
$$

