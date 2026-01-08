Agora que entendemos a funcionamento dos [[Circuitos RLC forçados]] queremos definir a potência nesses circuitos. Sabemos que a potência fornecida pela [[Fontes de Corrente Alternada]] é dada por:

$$
P(t) = V(t)I(t) = V_0\sin{(\omega t + \phi)}\times \dfrac{V_0}{Z}\sin{(\omega t)} = \dfrac{(V_0)^2}{Z}\sin{(\omega t + \phi)}\sin{(\omega t)}
$$

Onde $Z$ é a [[Impedância]], $V_0/Z$ é a amplitude da [[Corrente]], $V_O$ a amplitude da tensão, $\omega$ é a frequência e $\phi$ a defasagem entre tensão e corrente. Usando a identidade trigonométrica do seno da soma, obtemos:

$$
P(t) = \dfrac{V_0^2}{Z}\sin^2{(\omega t)} \cos{(\phi)} + \dfrac{V_0^2}{Z}\cos{(\omega t)} \sin{(\phi)}
$$

Nesse caso, a potência média é:

$$
\langle P(t) \rangle = \dfrac{1}{T}\int_0^T \dfrac{V_0^2}{Z}\sin^2{(\omega t)} \cos{(\phi)} + \dfrac{1}{T}\int_0^T \dfrac{V_0^2}{Z}\cos{(\omega t)} \sin{(\phi)} = \dfrac{V_0^2}{2Z}\cos{(\phi)}
$$

Que pode ser escrito em termos do [[Valor Eficaz ou RMS]] da tensão e da corrente como:

$$
\langle P(t) \rangle = \dfrac{V_0}{2Z}\cos{(\phi)} = I_{rms}V_{rms}\cos{(\phi)}
$$

Damos então ao $\cos{(\phi)}$ o nome de **fator de potência** e podemos escrevê-lo como sendo:

$$
\cos{(\phi)} = \dfrac{R}{Z}
$$

E podemos então escrever a **potência média** como sendo:

$$
\langle P(t) \rangle = R(I_{rms}(\omega))^2
$$

Note que a corrente é uma função da frequência, já que:

$$
I_{rms}(\omega) = \dfrac{1}{\sqrt 2}\dfrac{V_0}{\sqrt{(R)^2 + \left(\omega L-\dfrac{1}{\omega C}\right)^2}}
$$

E no caso especial onde onde a frequência angular é a frequência de [[Ressonância]] temos:

$$
\langle P(t) \rangle = \dfrac{(V_{rms})^2}{R}
$$

