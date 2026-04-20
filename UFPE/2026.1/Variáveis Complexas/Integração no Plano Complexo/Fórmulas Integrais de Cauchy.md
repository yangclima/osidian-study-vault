Até agora vimos resultados que mostram correspondências entre os elementos do cálculo com variáveis reais no cálculo com [[Funções Complexas]], quanto a sua [[Diferenciabilidade e Analiticidade]] e as [[Integrais Complexas]], o próximo resultado, denominado de **Fórmula de Cauchy** é extremamente interessante, estranho e não tem correspondências no cálculo real:

> Seja $f(z)$ uma função complexa analítica em um domínio simplesmente conexo $D$ e seja $C$ um contorno fechado simples totalmente contido em $D$, então, para qualquer ponto $z_0$ no interior de $C$ vale que:
> $$f(z_0) = \dfrac{1}{2\pi i }\oint_C\dfrac{f(z)}{z-z_0}dz$$

De forma similar, podemos, ao invés de exigir um domínio simplesmente conexo, que não estará explicitamente definido em muitos dos casos, exigir a analiticidade de $f(z)$ nos pontos interiores a curva $C$, obtendo:

> Se uma função $f(z)$ for analítica em um contorno simples e fechado $C$ e todos os pontos internos a ele e se $z_0$ for um dos pontos internos a $C$, então: $$f(z_0) = \dfrac{1}{2\pi i}\oint_C\dfrac{f(z)dz}{z-z_0}$$

O estranho dessa fórmula é a relação que ela estabelece entre o valor de uma função num certo ponto e os valores dela num contorno simples fechado que o contém, algo que não existe no cálculo com variáveis reais.

A partir desse teorema podemos ainda chegar na segunda fórmula de Cauchy, ou fórmula de Cauchy para derivadas que estabelece:

> Se uma função $f(z)$ é analítica em um domínio simplesmente conexo $D$, e  $C$ é um contorno fechado simples qualquer totalmente posicionado em $D$, então, para qualquer ponto $z_0$ no interior de $D$:
> $$f^{(n)}(z_0) = \dfrac{n!}{2\pi i}\oint_C \dfrac{f(z)}{(z-z_0)^{n+1}}dz$$

Isto é, podemos calcular qualquer derivada da função $f(z)$ através de uma integral de contorno sobre um contorno $C$ contido em seu domínio, ou de forma ainda mais poderosa, calcular a integral de contorno de uma função através das derivadas de outra. Além disso, esse teorema tem várias consequências interessantes:

> Seja $f(z)$ uma função analítica em um domínio simplesmente conexo $D$, então $f(z)$ possui derivadas de todas as ordens em todos os pontos $z$ nesse domínio e suas derivadas são funções analíticas em $D$

> Se a função $f(z)$ for contínua em um domínio simplesmente conexo $D$, se $\oint_Cf(z)dz = 0$ para qualquer contorno fechado simples $C$ em $D$, então $f(z)$ é analítica em $D$.

> As únicas funções inteiras limitadas são as funções constantes