---
tags:
  - anky
index: 6
---
A lei de Gauss é uma poderosa ferramenta matemática que podemos utilizar para calcular o [[Campo Elétrico]] de alguns tipos de corpos que possuem certos tipos de simetria e que seriam difíceis de calcular utilizando apenas a [[Lei de Coulomb]]. Para definir a lei de Gauss, que é uma espécie de relação de grandezas, precisamos entender um novo conceito: O **fluxo elétrico** ($\Phi_E$).

![[fg3_007.png]]

O fluxo elétrico pode ser interpretado como uma medida da perpendicularidade do campo elétrico com relação a uma superfície, ou como uma forma de mensurar a quantidade de linhas de campo que passam por uma superfície, para uma superfície plana de área $A$ e vetor normal $\hat n$ e um [[Campos escalares e vetoriais|campo vetorial]] uniforme $\vec E$ que faz um ângulo $\theta$ com $\hat n$, o fluxo elétrico pode ser definido como:

$$
\Phi_E = \vec{E} \cdot \vec{A} = \left(\vec{E} \cdot \hat{n}\right)A = AE\cos{\theta} 
$$

Essa expressão pode ser generalizada para qualquer tipo de de superfície se dividirmos essa superfície em infinitos fragmentos infinitesimais de área $dA$ que multiplicado pelo vetor unitário normal ao fragmento $\hat n$ se torna $d\vec{A}$, então somando esses elementos, obtemos:

$$
\Phi_E = \iint\limits_{S} \vec{E}\cdot d\vec{A}
$$
Sabendo disso, a Lei de Gauss, define então:

> O Fluxo elétrico sobre um superfície fechada é proporcional à carga envolvida pela superfície.

Ou seja:

$$
\Phi_E = \iint\limits_{S} \vec{E}\cdot d\vec{A} \propto Q_{enc}
$$

Além disso, a constante de proporcionalidade é o inverso da **constante de permissividade do vácuo** ($\varepsilon_0$), ou seja:

$$
\Phi_E = \iint\limits_{S} \vec{E}\cdot d\vec{A} = \dfrac{Q_{enc}}{\varepsilon_0}
$$

Essa relação é muito útil para calcular o campo elétrico de corpos que possuem simetria planar, cilíndrica ou esférica, como planos ou fios infinitos, esferas ou cascas de esferas e a aplicação dessa lei nesse obtivo pode ser feita seguindo alguns passos simples:

1. Analise e encontre o tipo de simetria que o corpo estudado possui
2. Determine a direção do campo elétrico
3. Decida quantas regiões do espaço são relevantes e diferentes de acordo com a distribuição de carga
4. Para cada região encontre uma superfície Gaussiana através da qual, para cada uma de suas partes, o campo elétrico seja constante ou nulo
5. Calcule o fluxo elétrico que passa através da superfície gaussiana
6. Calcule a carga contida em cada superfície gaussiana
7. Escreva ambos os lados da Lei de Gauss e resolva a equação isolando o campo elétrico $E$
