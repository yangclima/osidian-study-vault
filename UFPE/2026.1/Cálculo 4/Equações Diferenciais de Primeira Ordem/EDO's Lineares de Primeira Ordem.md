As EDO's lineares de primeira ordem são as mais simples e provavelmente as mais úteis [[Equações Diferenciais]] que existem e em geral são funções da forma:

$$
A(t)\dfrac{dx}{dt} + B(t)x(t) = C(t)
$$

Onde $A(x)$ e $B(x)$ são denominados **Coeficientes da equação**, e caso os coeficientes sejam independentes de $x$, dizemos que se trata de uma EDO Linear de coeficientes constantes.

Como $A(x) \neq 0$ (Afinal, caso $A(x)$ fosse igual a 0, não teríamos uma equação diferencial) podemos dividir o lado esquerdo da equação por $A(x)$ e simultaneamente multiplicar o lado direito por $A(x)$, obtendo:

$$
\dfrac{dx}{dt} + p(x)x(t) = q(t) \tag{1}
$$

Essa forma da equação diferencial é chamada então de **forma padrão da EDO linear de 1ª Ordem**, além disso, no caso específico em que $q(t) =0$ dizemos que esta equação é **homogênea**, caso contrário ela é **não homogênea**. Por exemplo, a seguinte equação é a Equação diferencial linear homogênea associada a equação 1:

$$\dfrac{dx}{dt} + p(x)x(t) = 0 \tag{2}$$

Esse tipo de equação diferencial serve, por exemplo, para representar uma série de fenômenos físicos, a exemplo da Lei de Newton do Resfriamento:

$$
\dfrac{dT}{dt} + \kappa T = \kappa T_e
$$

Como veremos depois, esses tipo de equação sempre tem solução e, além disso, aplica-se a elas o poderoso **princípio da superposição**.
