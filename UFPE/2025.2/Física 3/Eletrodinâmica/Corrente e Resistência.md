Até então, estudamos objetos e situações de tal forma que, mesmo considerando o efeito do [[Campo Elétrico]] e a forças que surgem pela sua interação com as cargas (Mensuradas segundo a [[Lei de Coulomb]]), considerávamos que os portadores de carga estavam parados, agora, porém, começaremos a ver situações onde existe um **fluxo de carga** através dos condutores os qual denominamos **Corrente**.

Corrente ( $I$ ) é o fluxo de carga elétrica que pode ser definido como taxa na qual as cargas fluem através de uma secção transversal de um condutor num determinado intervalo de tempo, assim, temos:

$$
I = \dfrac{dq}{dt}
$$

Ou, para intervalos de tempo e variações de carga finitos, a corrente média:

$$
I_m = \dfrac{\Delta Q}{\Delta t}
$$

Assim, a unidade de corrente é *Coulomb por segundo* apelidada de *Ampère* em homenagem ao cientista André-Marie Ampère, ou seja:

$$
Und(I) = \dfrac{C}{s} = [A]
$$

Note que como a corrente é um fluxo, para definí-la completamente precisamos definir também sua direção, **por convenção, adotamos a direção da corrente como a direção na qual as cargas positivas estão fluindo**. 

Entretanto, a corrente é um fenômeno macroscópico, então, utilizamos um conceito complementar para possibilitar o completo entendimento desse fenômeno, a **densidade de corrente** ($\vec{J}$) uma grandeza vetorial que pode ser pensada como uma corrente sobre área, perdendo assim a dependência que a corrente tem do condutor, definimos então:

$$
I = \iint\limits_\text{area} \vec{J} \,d\vec{A}
$$

Experimentalmente, descobriu-se que em alguns materiais, denominados materiais ôhmicos,  a exemplo dos metais em geral, a densidade de corrente $\vec{J}$ é proporcional  ao campo elétrico externo por uma constante de proporcionalidade $\sigma$ denominada **condutividade elétrica do material** (A unidade de medida de $\sigma$ é *Siemens* - $S$) que mede a capacidade do material de conduzir eletricidade, ou seja:

$$
\vec{J} = \sigma \vec{E}
$$

Essa relação é denominada versão microscópica da **Lei de Ohm** em homenagem ao cientista *George Ohm*, e sua versão macroscópica é:

$$
\Delta V = RI
$$

Onde $R$ é denominada a **Resistência** do condutor e dada pela relação:

$$
R = \dfrac{\rho L}{A} = \dfrac{L}{\sigma A}
$$

Onde $\rho$ é a **resistividade elétrica do material** (A unidade de medida de $\rho$ é *Ohm* - $\Omega$) que mede a resistência que o material oferece a passagem de corrente e pode ser considerada como o inverso da condutividade, ou seja, temos que $\rho = 1/\sigma$, $L$ é o comprimento do condutor e $A$ a sua área de secção transversal.

Além disso, a resistividade do material varia com a sua temperatura segundo a seguinte relação:

$$
\rho = \rho_0 (1 + \alpha\Delta T)
$$

Onde $\alpha$ é chamado de coeficiente térmico de resistividade do material