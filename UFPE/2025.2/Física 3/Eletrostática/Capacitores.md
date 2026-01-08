---
tags:
  - anky
---
Um capacitor é um aparato capaz de armazenar [[Carga]] através do campo elétrico e é composto basicamente por dois condutores que possuem cargas iguais em magnitude e opostas em sinal. 

Durante o processo de carregamento de um **capacitor**, uma carga $Q$ é transferida de um condutor para o outro (considerando que os dois estão inicialmente neutros), assim um adquire uma carga $+Q$ e o outro uma carga $-Q$, de tal forma que surge no capacitor uma [[Potencial elétrico|diferença de potencial]] $\Delta V$ com o condutor positivamente carregado em uma potencial maior que o negativamente carregado.

Experimentalmente, descobriu-se que a magnitude da carga armazenada em um capacitor é diretamente proporcional a magnitude da diferença de potencial $\Delta V$ entre os condutores por uma constante de proporcionalidade $C$ chamada de **capacitância** (Por convenção, positiva) que pode ser fisicamente interpretada como a capacidade de um capacitor de armazenar carga elétrica para uma dada diferença de potencial, portanto, temos:

$$
Q = C |\Delta V|
$$

A unidade de medida da capacitância é *Coulomb por Volt*, apelidada de *Faraday* em homenagem ao renomado cientista *Michael Faraday*, assim, temos:

$$
Und \ (C) = \dfrac{C}{V} = [F] 
$$

Nos diagramas de circuitos elétricos os capacitores são representados da seguinte forma:

![[fg3_008.png|center]]

E os principais tipos de capacitores são os **capacitores de placas paralelas**, **capacitores esféricos** e **capacitores cilíndricos**, cada um tem a sua própria fórmula de capacitância obtida encontrando-se os valores para a [[Carga]] e para o [[Potencial elétrico]] ($C = Q/|\Delta V|$) através do [[Campo Elétrico]], em geral, utilizando a [[Lei de Gauss]]. Além disso, vale a pena ter em mente que para a utilização da lei de Gauss nesse sentido é necessário desconsiderar os efeitos de borda, variações de campo elétrico que surgem nas bordas dos capacitores de placas paralelas e nas extremidades dos capacitores cilíndricos mas que são desprezíveis para dimensões macroscópicas de capacitores.

Uma das grandes utilidades dos capacitores é o armazenamento de energia que ocorre em função do armazenamento de carga e da presença de uma diferença de potencial, nesse caso, essa energia, por conservação, equivale ao trabalho realizado para transferir a carga entre os condutores, portanto:

$$
U_E = \int \limits_0^Q \Delta V dq = \int \limits_0^Q \dfrac{q}{C} dq = \dfrac{Q^2}{2C} = \dfrac{Q|\Delta V|}{2} = \dfrac{C|\Delta V|^2}{2}
$$
# Densidade de energia elétrica
Imaginando que a energia é de fato armazenada no campo elétrico podemos ainda pensar em uma grandeza que mensure a energia armazenada por volume, do campo elétrico, a **densidade de energia** ($u_E$):

$$
u_E = \dfrac{U_E}{\text {Volume}} = \dfrac{\varepsilon_0 E^2 }{2}
$$
Que se relaciona com a própria energia potencial elétrica do capacitor seguindo a seguinte relação:

$$
U_E = \int\limits_\text{volume} u_E \, dV
$$