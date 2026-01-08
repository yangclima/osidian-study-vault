---
tags:
  - anky
---
Experimentalmente foi obtido que a [[Corrente]] em um condutor é proporcional ao [[Potencial elétrico]] aplicado a esse condutor, ou seja:

$$
I \propto \Delta V
$$

Definindo essa relação, deve então haver uma constante de proporcionalidade, como propriedade do condutor que meça o quanto esse condutor é suscetível a passagem de corrente dado um determinado potencial elétrico, essa grandeza, nós chamamos de **Resistência** e denotamos por $R$, assim, chegamos à relação:

$$
\Delta V = R\cdot I
$$

Denominada, Lei de Ohm. Essa resistência é uma propriedade macroscópica do condutor e no Sistema Internacional, sua unidade é o "Ohm" ($\ohm = V\cdot A^{-1}$) em homenagem ao cientista *George Ohm*. 

Podemos imaginar que essa resistência deve ter uma certa dependência da geometria e do material do qual se constitui o condutor. Pare para pensar: Um fio mais robusto deve permitir a passagem da [[Corrente]] com uma maior facilidade e na mesma medida, um condutor mais comprido deve ser mais difícil de se atravessar do que um condutor curto, além disso, é sabido que os elétrons atravessam alguns materiais mais facilmente que outros devido as propriedades microscópicas e atômicas desses materiais, em vista disso podemos usar as seguintes relações para definir a resistência:

$$
R = \dfrac{\rho L}{A} = \dfrac{L}{\sigma A}
$$

Onde $L$ é o comprimento do condutor, $A$ é a área da secção transversal desse condutor e $\rho$ é denominada **resistividade**, uma propriedade intrínseca de cada material, $\sigma$ por outro lado é o recíproco da resistividade, denominada **condutividade**, grandezas que se relacionam segundo a equação:

$$
\rho = \dfrac{1}{\sigma}
$$

E as unidades da **resistividade** e da **condutividade** no Sistema Internacional são respectivamente $\ohm \cdot m$ (*Ohm metro*) e $S\cdot m^{-1}$ (*Siemens por metro*). 

Ma uma vez nos esbarramos então no problemas de que estamos descrevendo fenômenos de ordem microscópica utilizando grandezas macroscópicas, nesse sentido, descobrimos experimentalmente que em alguns materiais, denominados materiais ôhmicos,  a exemplo dos metais em geral, a densidade de corrente $\vec{J}$ é igual ao campo elétrico externo multiplicado pela **condutividade elétrica do material**, ou seja:

$$
\vec{J} = \sigma \vec{E}
$$

Essa relação é denominada versão microscópica da **Lei de Ohm**.

Por fim, um fato notável é que a resistividade do material varia com a sua temperatura segundo a seguinte relação:

$$
\rho = \rho_0 (1 + \alpha\Delta T)
$$

Onde $\alpha$ é chamado de coeficiente térmico de resistividade do material.

Num circuito, elementos que possuem a função de oferecer resistência são chamados de **resistores** e seu símbolo é:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz}[american voltages, thick]
\draw 
(0,0)to[R=$R$](4,0);
\end{circuitikz}
\end{document}
```