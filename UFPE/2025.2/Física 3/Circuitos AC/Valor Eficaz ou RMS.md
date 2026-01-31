Agora que passamos a trabalhar com [[Fontes de Corrente Alternada]] e [[Circuitos RLC forçados]] onde tanto [[Corrente]] como [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão]] aparecem como grandezas variáveis no tempo é conveniente definir o que chamamos de **valor eficaz de tensão** e **valor eficaz de corrente**

O valor eficaz é também chamado de RMS ou *root-mean-square*, a questão é que como a corrente e a tensão aparecem na forma de uma função senoidal, de nada adiantaria considerar suas médias $\langle I \rangle$ e $\langle V \rangle$ já que estas são zero devido ao comportamento da função seno:

$$
\langle I \rangle = \dfrac{1}{T}\int_0^T I_0\sin{(\omega t)} = \dfrac{-I_0}{T\omega}\cos{(\omega t)}\Bigg{|}_0^T = 0
$$

É conveniente então considerar o **valor eficaz** corrente que equivale a raiz da média do quadrado, isto é:

$$
I_{rms} = \sqrt{\langle I^2 \rangle} = \sqrt{\dfrac{1}{T}\int_0^T I_0^2\sin^2(\omega t)dt}= \dfrac{I_0}{\sqrt 2}
$$

Esse valor, no caso de um circuito puramente resistivo pode ser pensado como o valor de corrente DC que produziria a mesmo aquecimento num resistor, por exemplo, isso deve-se a fato de que, como num resistor a potência dissipada é:

$$
P(t) = I(t)^2R = R\left(\dfrac{1}{T}\int_0^T I_0^2\sin^2(\omega t)\right) = R(I_{rms})^2
$$

Então definimos os valores  eficazes de tensão e corrente como sendo:

$$
I_{rms} = \dfrac{I_0}{\sqrt 2}
$$

$$
V_{rms} = \dfrac{V_0}{\sqrt 2}
$$

Onde $I_0$ e $V_0$ são os valores da amplitude da corrente e da tensão respectivamente. 

Um fato interessante é que o valor eficaz é que é utilizado para designar uma certa tensão, por exemplo, a tensão $220V$ é o valor eficaz de uma tensão de caráter senoidal de amplitude $V_0 = 220 \times \sqrt 2 \approx 311V$.