A consistência interna das **[[Equações de Maxwell no domínio do tempo|Equações de Maxwell]] no domínio do tempo** implica a **conservação local da carga elétrica**. 

Essa propriedade é expressa matematicamente pela chamada **equação da continuidade para a carga**, que pode ser deduzida diretamente a partir da **[[Lei de Ampére|lei de Ampére-Maxwell]]**.

Partindo da forma diferencial dessa lei,

$$
\nabla \times \vec H = \vec J + \frac{\partial \vec D}{\partial t}
$$

e tomando o [[Divergente]] de ambos os lados, obtemos

$$
\nabla \cdot (\nabla \times \vec H) = \nabla \cdot\left(\vec J + \frac{\partial \vec D}{\partial t}\right)
$$

Porém, como o divergente do [[Rotacional]] de um campo suficientemente regular é sempre nulo:

$$
0 = \nabla \cdot \vec J + \nabla \cdot \frac{\partial \vec D}{\partial t}
$$

E como, pela [[Lei de Gauss para Cargas|Lei de Gauss]] $\nabla \cdot \vec D = \rho$ temos:

$$
0 = \nabla \cdot \vec J + \frac{\partial \rho}{\partial t}\implies \nabla \cdot \vec J = -\frac{\partial \rho}{\partial t}
$$

Essa expressão é denominada **equação da continuidade para a carga elétrica** e expressa a conservação local da carga: variações temporais da densidade de carga em um ponto do espaço estão necessariamente associadas a fluxos de corrente elétrica.

Uma interpretação mais intuitiva dessa relação pode ser obtida aplicando o **[[Teorema do Divergente]]**, o que conduz à sua forma integral:

$$
 \dfrac{dQ}{dt} =\dfrac{d}{dt} \iiint_V \rho\, dV = -\iint_S (\vec J \cdot \hat n)dA
$$

Essa equação afirma que a taxa de variação da carga total $Q$ contida em um volume $V$ é igual ao **fluxo líquido de corrente elétrica que atravessa a superfície fechada $S$** que delimita esse volume. Em outras palavras, a carga em um volume só pode variar se houver corrente elétrica entrando ou saindo dele, expressando matematicamente o princípio de conservação da carga.