No cálculo com variáveis reais, um dos mais importantes, senão o mais importante é [[Primeiro teorema fundamental do cálculo]], que foi estendido posteriormente para o [[Teorema fundamental das integrais de linha]], ambos relacionam uma integral de uma função $f(z)$ com sua primitiva $F(z)$, uma função tal que $F^\prime(z) = f(z)$. 

Essa definição é importante pode ser estendida uma vez mais para as [[Integrais Complexas]], isto é, integrais envolvendo [[Funções Complexas]].

Sabemos que se $z_0$ e $z_1$ são pontos de um domínio $D$, uma integral de contorno $\oint_C f(z)dz$ **Independe do caminho se** apresentar o mesmo valor para todos os caminhos $C$ em $D$ que tem ponto inicial em $z_0$ e ponto final em $z_1$, a partir disso e do [[Teorema de Cauchy-Goursat]] aplicado sobre dois contornos quaisquer entre esses pontos, chegamos ao seguinte teorema:

> Seja $f(z)$ uma função complexa analítica em um domínio simplesmente conexo $D$ e seja $C$ um contorno qualquer nesse domínio, Então $f_C(z)dz$ independe do caminho.

Ou seja,  num domínio simplesmente conexo de uma função $f(z)$, a integral entre dois pontos $z_0$ e $z_1$ é independente do caminho, isto é, tem o mesmo valor para qualquer percurso entre eles, o que nos permite sempre calcular essa integral através do caminho mais simples

Uma forma ainda mais simples de calcular uma integral desse tipo é utilizando a antiderivada da função $f(z)$, chegando a nossa versão complexa do teorema fundamental do cálculo:

> Seja $f(z)$ uma função complexa contínua em um domínio $D$ e seja $F(z)$ uma antiderivada de $f(z)$ nesse domínio, para qualquer contorno $C$ em $D$ com ponto inicial $z_0$ e ponto final $z_1$: 
> $$\int_C f(z)dz = F(z_1) - F(z_0)$$

Além disso, as asserções a respeito desse teorema nos leva a um outro:

> Seja $f(z)$ uma função analítica em um domínio simplesmente conexo $D$. Então, $f(z)$ possui uma antiderivada em $D$ ou seja, existe uma função $F(z)$ tal que $F^\prime(z) = f(z)$ para todo $z$ em $D$.

Essas definições levam a necessidade de se tomar alguns cuidados ao realizar essas operações, por exemplo, sabemos que a derivada da [[Funções Exponencial e Logarítmica Complexas#Função Logarítmica Complexa|Função Logarítmica Complexa]] ($Log(z)$) é $1/z$, isto é, essa função é uma primitiva para $f(z) = 1/z$, entretanto, ela não é analítica, sendo portanto, primitiva, apenas nos casos em que o domínio $D$ não envolve os buracos de analiticidade da funções $f(z)$ e $Ln(z)$.
