Enquanto a [[Lei de Gauss para Cargas]] é a [[Equações de Maxwell|equação de Maxwell]] que conecta a presença de [[carga]] no espaço com a existência de um [[Campo Elétrico]] estático, a [[Lei de Ampére]], outra equação de Maxwell conecta a existência de um fluxo de cargas estático ([[Corrente]]) com a existência de um [[Campo Magnético]].

A Lei de Ampére no regime magnetostático define que para o caso de campos magnéticos invariantes no tempo, vale que a [[Integrais de linha|integral]] do campo magnético $\vec H$ ao longo de qualquer [[Parametrização de curvas|curva]] fechada $C$ é igual a [[Integrais de superfície|integral de superfície]] da densidade de corrente $\vec J$ fluindo através da superfície $S$ delimitada por essa curva, isto é:

$$
\oint_C \vec H \cdot d\vec r = \iint_S \vec J \cdot d\vec A
$$

Note que, nesse caso, é relevante levar em consideração a convenção que estabelecemos para o [[Teorema de Stokes]], isto é, tomando a curva e a superfície positivamente orientadas.

Assim como $\vec D$, $\vec H$ não é um novo campo mas um campo auxiliar que nos permite mensurar o efeito do campo magnético em meios materiais, para o caso do vácuo, temos que:

$$
\vec B = \mu_0 \vec H \implies \oint_C \vec B \cdot d\vec r = \mu_0\iint_S \vec J \cdot d\vec A
$$

Vale ressaltar, mais uma vez, que as equações de Maxwell são lineares o que abre espaço para a aplicação do princípio da superposição que para o caso das correntes se manifesta através da [[UFPE/2025.2/Física 3/Magnetostática/Lei de Biot-Savart]] que para $\vec H$ se escreve da seguinte forma:

$$
\vec H = \iiint_{V^\prime} \frac{\vec J^\prime \times (\vec r- \vec r^\prime)}{4\pi |\vec r- \vec r^\prime|^3}
$$

E explica como uma distribuição de corrente $\vec J^\prime$ numa posição $\vec r^\prime$  dentro de um volume $V^\prime$ contribui para o campo auxiliar $\vec H$ numa posição $\vec r$.