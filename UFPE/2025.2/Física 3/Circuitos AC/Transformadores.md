Um transformador é um dispositivo que se utiliza do fenômeno da [[Indução mútua]] para aumentar ou diminuir a [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]] alternada num circuito AC.

Tipicamente, esses dispositivos são compostos por duas bobinas envolvendo um núcleo de ferro, a primeira bobina, denominada **bobina primária** possui $N_1$ espiras e está conectada a uma [[Fontes de Corrente Alternada|fonte de corrente alternada]] enquanto a segunda, denominada **bobina secundária** possui $N_2$ espiras e está conectada a uma carga de [[Resistência|resistência]] $R_2$ (Aqui este resistor faz o papel de uma carga qualquer, um outro dispositivo conectado ao transformador), o núcleo de ferro, por sua vez, cumpre o papel de amplificar o [[Campo Magnético]] das espiras e de conduzir o fluxo magnético entre estas bobinas praticamente sem nenhum "vazamento" de fluxo.

![[fg3_023.png|center]]

A corrente na bobina primária induz um fluxo magnético ao longo da própria bobina e portanto, pela [[Lei de Faraday]] temos:

$$
V_1 = -N_1\cdot\dfrac{d\Phi_B}{dt}
\tag{1}
$$

E considerando que não há perdas de [[Fluxo magnético]], isto é, todo o fluxo da bobina primária é conduzido pelo núcleo até a bonina secundária, então, na bobina secundária, deve surgir uma [[Força eletromotriz]] alternada $V_2$ dada por:

$$
V_2 = -N_2 \dfrac{d\Phi_B}{dt}
\tag{2}
$$

No caso ideal, ou seja, ignorando tanto o "vazamento" de fluxo quanto as perdas por efeito joule nas bobinas e no núcleo e os efeitos das [[Correntes de Foucault]], então, a potência da [[Fontes de Corrente Alternada|fonte]] deve ser integralmente transferida para a bobina secundária, então:

$$
V_1I_1 = V_2I_2
$$

Além disso, o fluxo magnético deve ser igual em ambas as bobinas, então, dividindo a equação $2$ pela equação $1$ obtemos:

$$
\dfrac{V_2}{V_1} = \dfrac{N_2}{N_1}
$$

Esta equação é conhecida como **Equação do transformador**, por fim, obtemos que:

$$
I_1 = \dfrac{V_2}{V_1}I_2 = \dfrac{N_2}{N_1}I_2 
$$

Ou seja, o valor $V_2/V_1$ ou $N_2/N_1$ pode ser encarado como um coeficiente de transformação do transformador.

Quanto a aplicação, os trafos podem ser classificados como **elevadores** ou *step-up* se aumentam a tensão, ou seja $V_2/V_1 > 1$ ou como trafos **redutores** se diminuem a tensão, ou seja, $V_2/V_1 < 1$.

