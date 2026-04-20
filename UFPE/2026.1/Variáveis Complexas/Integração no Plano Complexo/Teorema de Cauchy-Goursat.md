O Teorema de Cauchy-Goursat é um dos mais importantes da análise complexa e depende de algumas das definições que vimos em [[Cálculo 3]], mas agora para [[Conjuntos de pontos no plano complexo]]. Já sabemos que um domínio $D$ no [[O plano complexo|plano complexo]] é um conjunto de pontos aberto e conexo, existem porém, os domínios **Simplesmente Conexos** ou **Multiplamente Conexos**, os primeiros são aqueles sem buracos onde qualquer contorno $C$ posicionado nesse domínio contém em seu interior apenas pontos do domínio, por outro lado, dizemos que um domínio é multiplamente conexo se ele, mesmo conexo, possui buracos, sendo duplamente conexo se possuir um buraco, triplamente conexo se possuir dois e assim por diante.

O Teorema de Cauchy, que pode ser demonstrado partindo do [[Teorema de Green]], enuncia então:

> Seja $f(z)$ uma [[Funções Complexas|função complexa]] [[Diferenciabilidade e Analiticidade|analítica]] em um **Domínio Simplesmente Conexo** $D$ e seja $f^\prime(z)$ sua derivada, contínua em $D$, então, para qualquer contorno fechado simples $C$ em $D$, vale que: $$\oint_Cf(z)dz = 0$$


Goursat posteriormente refinou ainda mais o teorema chegando a conclusão do chamado teorema de Cauchy-Goursat, dispensando a hipótese de continuidade de $f^\prime(z)$:

> Seja $f(z)$ uma [[Funções Complexas|função complexa]] [[Diferenciabilidade e Analiticidade|analítica]] em um **Domínio Simplesmente Conexo** $D$ então, para qualquer contorno fechado simples $C$ em $D$, vale que: $$\oint_Cf(z)dz = 0$$

Isto nos leva a conclusão de que, se uma função $f$ for analítica em todos os pontos de um contorno $C$ simples e fechado e nos pontos internos a esse contorno, então vale que sua [[Integrais Complexas|integral complexa]] sobre este contorno, é zero, de modo que qualquer função inteira, tal como $e^z$, $\sin{z}$, $\cos{z}$... tem sua integral de contorno nula para qualquer contorno fechado simples.

# Princípio da deformação dos contornos
Um princípio muito importante que surge do teorema de Cauchy-Goursat é chamado de **princípio da deformação dos contornos** e estabelece que o valor da integral de contorno de uma função $f(z)$ sobre um contorno $C$ não muda ao deformarmos esse contorno sobre uma região em que $f(z)$ seja analítica, o que permite que calculemos integrais sob contornos muito complexos através de contornos mais simples.

Desse princípio, deriva uma interessante observação a respeito das integrais do tipo 

$$\oint \dfrac{1}{(z-z_0)^n}$$

De modo que pode ser demonstrado que esta integral é igual a $2\pi i$ para $n = 1$ e igual a $0$ para qualquer outro valor de $n$, isso também permite inferir que apesar de que é suficiente que uma função seja analítica em todo um domínio $D$ para que sua integral de contorno sobre um contorno $C$ contida nesse domínio seja $0$, essa condição não é necessária.

Isso abre margem para um sutil funcionamento do método de integração por frações parciais em integrais complexa, usando a fórmula:

$$\oint \dfrac{1}{(z-z_0)^n} = \begin{cases}0, \ \text{se } \ n \neq 1 \\ 2\pi i , \ \text{se } \ n = 1\end{cases}$$

A mesma prova que leva a esse princípio nos traz a um teorema muito útil na resolução de integrais complexas em domínios multiplamente conexos:

> Sejam $C, C_1, C_2, \cdots, C_n$ curvas fechadas simples todas com orientação positiva, de modo que $C_1, C_2, \cdots, C_n$ sejam internas a $C$ mas não tenham pontos internos em comum, se a função $f(z)$ for analítica em todos os pontos que são internos a $C$ e externos a cada contorno $C_1, C_2, \cdots, C_n$ então vale que: $$\oint f(z)dz = \sum_{k= 1}^n \oint_{C_k}f(z)dz$$


Isso é útil no caso em que temos uma função $f(z)$ que não é analítica em mais de um ponto do interior do contorno de interesse $C$, podemos então reescrever a integral de contorno de $f(z)$ como uma soma das integrais de contorno sobre os contornos que circundam cada um dos pontos de não analiticidade de $f$.