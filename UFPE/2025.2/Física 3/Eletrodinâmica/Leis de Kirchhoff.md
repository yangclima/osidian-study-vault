As leis de Kirchhoff são os princípios fundamentais da análise de [[Circuitos DC|circuitos]] e permitem a análise de circuitos complexos onde a lei de Ohm já não é mais suficiente. As Leis de Kirchhoff são obtidas através de definições a respeito da conservação de carga e de energia e são duas: **A lei de Kirchhoff das Correntes (LKC)** e **a lei de Kirchhoff das tensões (LKT)**.

# A lei de Kirchhoff das correntes
A primeira lei de Kirchhoff, a das correntes, diz que a soma das correntes que  entram em um nó num [[Circuitos DC|circuito DC]] deve ser igual a soma das correntes que sai desse mesmo nó, ou seja:

$$
\sum \ I_{\text{entra}} = \sum \ I_{\text{sai}}
$$

Assim, temos, por exemplo:

![[fg3_011.png|center]]

# A lei de Kirchhoff das tensões
A lei de Kirchhoff das Tensões, por outro lado, diz que a soma das quedas de tensão ao longo de quaisquer elementos que formam uma malha fechada em um circuito DC deve ser sempre igual a $0$, ou seja, em uma malha fechada:

$$
\sum \ \Delta V = 0
$$

Essa lei é a base para a análise de malha em circuitos DC, a ideia é escolher um sentido arbitrário e percorrer as malhas do circuito mensurando as quedas de tensão devido a cada elemento do circuito, considerando positiva a contribuição dos  elementos que promovem, através de si um aumento na tensão e negativa a daqueles que promovem um aumento de tensão.

A contribuição de uma fonte de tensão é igual a [[Força eletromotriz]] fornecida, sendo assim positiva caso a percorramos do negativo para o positivo e negativa caso o contrário..

A contribuição de um [[Corrente e Resistência|resistor]] é, pela lei de Ohm, igual a $IR$, sendo positiva caso promova um aumento de potencial no sentido considerado e negativa caso contrário.

A contribuição de um [[Capacitores|capacitor]] é $\dfrac{Q}{C}$ e seu sinal é definido pelo mesmo critério que o sinal para o resistor.
