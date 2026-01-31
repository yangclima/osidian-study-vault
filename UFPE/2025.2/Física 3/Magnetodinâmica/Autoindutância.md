---
tags:
  - anky
---
Já vimos que o fenômeno da [[Indução mútua]] ocorre pelo [[Fluxo magnético]] devido a variação do [[Campo Magnético]] de um condutor, por conta de uma [[Corrente]] variável, sob um outro condutor, entretanto, um fenômeno parecido ocorre num condutor único, ou seja, sem necessidade da existência do segundo condutor, esse fenômeno é o que chamamos de **autoindutância** ou simplesmente **indutância**.

Considere um bobina de $N$ espiras por onde passa uma corrente $I$ no sentido anti-horário

![[fg3_022.png|center]]

Se essa corrente $I$ varia no tempo, o campo magnético gerado por ela, também varia e portanto, o fluxo magnético, assim, de acordo com a [[Lei de Faraday]], surgirá nessa bobina uma corrente que pela [[Lei de Lenz]] deve se opor a essa variação, sendo assim, caso $\dfrac{dI}{dt}>0$ a corrente induzida fluirá no sentido horário e caso $\dfrac{dI}{dt} < 0$ no sentido horário.

Essa corrente se manifesta por meio de uma [[Força eletromotriz]] a qual denominamos **força eletromotriz autoinduzida**, denotada por $\varepsilon_L$ e matematicamente definida da seguinte forma:

$$
\varepsilon_L = -N\cdot\dfrac{d\Phi_{B,espira}}{dt} = -N\cdot\dfrac{d}{dt} \iint\limits_{espira} \vec B \cdot d\vec A
$$

Porém, esse fluxo é proporcional a corrente, então, uma outra forma de definir matematicamente essa força eletromotriz é:

$$
\varepsilon_L = -L\cdot \dfrac{dI}{dt}
$$

Onde $L$ é uma constante de proporcionalidade entre a força eletromotriz que surge e a corrente que a gera, além disso, $L$ pode ser interpretada fisicamente como a resistência do condutor a mudança de corrente. Assim, utilizando essas duas relações, podemos deduzir:

$$
L = \dfrac{N\cdot\Phi_{B,espira}}{I} = \dfrac{N\cdot\Phi_{B}}{I}
$$

Assim como para a indutância mútua, a unidade no Sistema Internacional para $L$ é o *Henry* ($H$).