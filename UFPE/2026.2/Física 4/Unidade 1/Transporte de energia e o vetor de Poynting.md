Um fato importantíssimo sobre as [[Maxwell e a previsão das Ondas Eletromagnéticas|ondas eletromagnéticas]] é a sua capacidade de transferir energia (tal qual as ondas mecânicas) e também momento (É possível dar uma pancada a distância), quanto a energia, isso já era de se esperar, afinal tanto o [[Campo Elétrico]] quanto o [[Campo Magnético]] tem densidades de [[Conservação de Energia|energia]] associadas, $u_e = \varepsilon_0E/2$ e $u_B = B^2/2\mu_0$, de modo que utilizando a relação entre as magnitudes dos campos numa onda eletromagnética podemos mostrar que a densidade de energia total uma onda eletromagnética é:

$$u = u_e + u_b = 2u_e = 2u_b = \varepsilon_0E^2 = \mu_0B^2$$

O que decorre do fato de que $u_e = u_b$ nessas ondas. Note também que $u$, como os campos aqui são funções do tempo e da posição, é também uma função dessas duas variáveis.

Agora, introduzimos uma nova notação para representar o fluxo de energia (Energia por tempo) por área (Potência sobre Área) com a unidade $[W/m^2]$ e podemos chegar a:

$$S = \frac{EB}{\mu_o}$$

Porém, como a energia tem uma direção de propagação igual a direção de propagação da onda, introduzimos o chamado **[[Vetor de Poynting]]** como sendo:

$$\vec S = \frac{\vec E \times \vec B}{\mu_0}$$

Apesar disso, o valor instantâneo de $\vec S$ é muito difícil de medir, isso por que, sendo uma função de seno quadrado, tem o dobro da frequência do seno, por isso, na prática, ao invés de lidarmos com esse valor, lidamos com seu valor médio $S_{méd}$ num dado intervalo de tempo $\Delta t$, valor conhecido como **Intensidade** $I$ da onda.

$$I = S_{méd} = \dfrac{E_m^2}{c\mu_0 } = \frac{E^2_{rms}}{c\mu_0}$$

Onde $E_m$ é a amplitude do campo elétrico da onda e $E_{rms}$ é o [[Valor Eficaz ou RMS]] do campo elétrico.


Note que a intensidade $I$ é ainda uma razão da potência sobre a área, ao lidar com [[Ondas Eletromagnéticas Planas]], não há muito o que falar sobre isso, mas quando temos uma fonte pontual de radiação eletromagnética, isotrópica (Emite igualmente em todas as direções), passamos a ter frentes de onda esféricas cuja área aumenta com o tempo, de modo que a intensidade cai com a distância por uma fator de $4\pi r^2$, isto é,  $I\sim 1/r^2$, isto é:


$$I = \frac{\text{Potência}}{\text{Área}} = \frac{P}{A}= \frac{P}{4\pi r^2}$$

Onde $P$ é a potência da fonte.