Nós sabemos que a energia pode ser armazenada tanto no [[Campo Elétrico]] quanto no [[Campo Magnético]], assim, como as ondas eletromagnéticas são compostas de ambos esses campos, elas podem então transportar energia.

Considere uma [[Ondas Eletromagnéticas Planas|Onda Eletromagnética Plana]] passando através de uma elemento infinitesimal de área $A$ e espessura $dx$.

Como a [[Capacitores#Densidade de energia elétrica|densidade de energia elétrica]] ($u_E$) e a [[Indutores#Densidade de energia magnética|densidade de energia magnética]] ($u_B$) são dadas por:

$$
u_E = \dfrac{\varepsilon_0 E^2 }{2} \ \ \ \ \ \ \text{e} \ \ \ \ \ \ u_B = \dfrac{B^2}{2\cdot\mu_0}
$$

Então a energia total armazenada no elemento infinitesimal é:

$$
dU = uAdx = \dfrac{1}{2}\left(\varepsilon_0 E^2 + \dfrac{B^2}{\mu_0}\right)Adx
$$

Mas, como as ondas eletromagnéticas se propagam na velocidade da luz, temos que o tempo que a onda demora para atravessar o elemento infinitesimal é dado por $dt = dx/c$, nesse caso, podemos substituir $dx$ por $cdt$ e então definir a **taxa de variação de energia por unidade de área** $S$ como:

$$
S = \dfrac{1}{A}\cdot\dfrac{dU}{dt} = \dfrac{c}{2}\left(\varepsilon_0 E^2 + \dfrac{B^2}{\mu_0}\right)
$$

Porém, como, pelas [[Equações de Maxwell]], $c = 1/\sqrt{\mu_0\varepsilon_0}$ e $E=cB$ podemos escrever:

$$
S = \dfrac{cB^2}{\mu_0} = c\varepsilon_0E^2 = \dfrac{EB}{\mu_0}
$$

Podemos então transformar essa taxa de variação em um vetor, atribuindo a ele a direção da propagação da onda, nesse caso:

$$
\vec S = \dfrac{\vec E \times \vec B}{\mu_0}
$$

Esse vetor é então chamado de **Vetor de Poynting**, em homenagem ao físico britânico *John Poynting*.

A partir desse conceito, podemos definir a **Intensidade de Onda** $I$ como a média temporal de $S$, ou seja (Para ondas senoidais planas):

$$
I = \langle S \rangle = \dfrac{E_0B_0}{2\mu_0}
$$

Por fim, para relacionar a intensidade de onda com a densidade de energia, notamos que:

$$
u_B = \dfrac{B^2}{2\mu_0} = \dfrac{(E/c)^2}{2\mu_0} = \dfrac{E^2}{2\mu_0c^2} = \dfrac{\varepsilon_0 E^2}{2} = u_E
$$

Nesse caso:

$$
\langle u \rangle = \langle u_E + u_B \rangle = \varepsilon_0 \langle E^2 \rangle = \dfrac{\varepsilon_0 E^2}{2} = \dfrac{\langle B^2 \rangle}{\mu_0} = \dfrac{B^2}{2\mu_0} 
$$

Portanto:

$$
I = \langle S \rangle = c\langle u \rangle
$$

E como a potência é $dU/dt$, então:

$$
\langle P \rangle = \langle S \rangle A = IA
$$

Definidos estes termos, vemos que o **Vetor de Poynting** representa a taxa com que a energia flui por unidade de área, então, podemos definir a variação de energia num volume fechado $V$ da seguinte maneira:

$$
\dfrac{dU}{dt} = - \iint\limits_V \vec S \cdot d\vec A
$$

