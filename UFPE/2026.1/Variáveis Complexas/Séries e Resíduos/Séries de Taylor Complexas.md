Como a relação entre um ponto $z$ no interior do circulo de convergência de uma [[Sequências e Séries complexas|Série de potências Complexa]] $\sum_{k=0}^\infty a_k(z-z_0)^k$ e o valor para o qual aquela série converge é unívoca, essa série de potências pode ser enxergada como uma função $f(z)$, tal que o valor $L$ para o qual a série converge no ponto $z$ é tomado como o valor de $f(z)$.

É importante ter em mente três propriedades das [[Séries de Potências|séries de potência]] em seu raio de convergência:

1. Uma série de potências representa uma [[Função]] contínua $f$ no interior do seu raio de convergência.
2. Uma série de potências pode ser [[Diferenciabilidade e Analiticidade|diferenciada]] termo a termo no interior do seu círculo de convergência de modo que a função $f^\prime$ obtida desse modo é ainda uma série de potências e mantém o mesmo raio de convergência de forma que **uma série de potências define uma função $f$ infinitamente diferenciável no seu círculo de convergência**.
3. Uma série de potências pode ser [[Integrais Complexas|integrada]] termo a termo no interior do seu círculo  de convergência para todo e qualquer contorno $C$ totalmente contido nesse círculo de modo que a série de potências assim obtida define uma função $F$ e possui o mesmo raio de convergência.

Suponhamos agora que uma dada série de potências representa uma função $f$ no interior de seu raio de convergência $|z-z_0| = R$, caso $R$ seja positivo ou infinito podemos chegar a conclusão de que $f$ é uma função analítica em se círculo de convergência e há uma relação entre os coeficientes $a_k$ e as derivadas de $f$ de modo que podemos escrever:

$$f(z) = \sum_{k=0}^{\infty} \dfrac{f^{(k)}(z_0)}{k!}(z-z_0)^k$$

Uma série que, para uma dada função $f$ qualquer é dita [[Séries de Taylor e Maclaurin|Série de Taylor]] para $f$ centrada em $z_0$. Para o caso particular em que $z_0 = 0$ chamamos essa série de **Série de Maclaurin**.

Daí surge o chamado teorema de Taylor: 

> Se uma dada [[Funções Complexas|função]] $f(z)$ é analítica em um determinado [[Conjuntos de pontos no plano complexo|Domínio]] $D$ e sendo $z_0$ um ponto tal que que $z_0 \in D$, então $f$ pode ser representada como
> $$f(z) = \sum_{k=0}^\infty\dfrac{f^{(k)}(z_0)}{k!}(z-z_0)^k$$
> Que é válida, isto é, converge, dentro do maior círculo $C$ centrado em $z_0$ e raio $R$ totalmente contido em $D$, ou seja, o maior círculo dentro do qual $f$ é analítica.


Podemos então encontrar o raio de convergência de uma série de Taylor como sendo a distância $R$ do centro $z_0$ da série até a **singularidade isolada** de $f(z)$ mais próxima, ou seja, o ponto mais próximo em que $f(z)$ deixa de ser analítica mas ainda é analítica para todos os pontos na sua vizinhança, isto é, um furo no domínio $D$ da função.

Algumas séries de Maclaurin importantes são:

$$
e^z = \sum_{k=0}^\infty\dfrac{z^k}{k!}
$$
$$
\sin{(z)} = \sum_{k=0}^\infty(-1)^k\dfrac{z^{2k+1}}{(2k+1)!}
$$
$$
\cos{(z)} = \sum_{k=0}^\infty(-1)^k\dfrac{z^{2k}}{(2k)!}
$$

Um fato importante que pode ser provado é que a expansão em séries de potência de uma função com centro em $z_0$ é única, isto é, a expansão de uma função analítica em séries de potências centrada em $z_0$ é a série e Taylor dessa função, não importa o método usado para obtê-la.