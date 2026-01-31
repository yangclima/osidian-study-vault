Um problema muito interessante e que em sua forma mais geral está relacionado ao movimento dos átomos, denominado **Movimento Browniano** é o chamado **Problema do Caminho aleatório**. A ideia é a seguinte:

> Considere um jogador que joga uma moeda honesta e se obtém cara se move um metro para frente, caso contrário, se move um metro para trás.

Podemos então mensurar o progresso do jogador através da sua distância com relação ao ponto inicial após $N$ lançamentos da moeda ($D_N$), porém como a [[Função probabilidade|probabilidade]] de ir para frente ou para trás é idêntica devemos esperar que em média o seu progresso seja $0$ (Para cada resultado possível onde o jogador alcança uma distância $D_N$ existe um resultado possível onde ele alcança uma distância $-D_N$, assim, os resultados sempre se cancelarão na média), entretanto, factualmente, quanto maior o número de lançamentos $N$, maior a probabilidade do jogador se afastar da origem, sendo assim, uma forma melhor de representar seu progresso é considerar o valor absoluto da distância $|D_N|$, evitando que distâncias iguais em módulo se cancelem na média, porém, é matematicamente mais conveniente, considerar o quadrado da distância $D_N^2$ como nossa medida de progresso.

Assim, o progresso médio do jogador é a "distância quadrática média" , denotado por $\langle D_N^2 \rangle$ e que também pode ser pensado como o "[[Esperança|valor esperado]]" ou "valor mais provável" para a distância quadrática do jogador após $N$ jogadas e podemos obter que esse valor mais provável é simplesmente $N$, isto é:

$$
\langle D_N^2 \rangle = N
$$

Ou, se quisermos algo como o valor com distância média em relação a origem podemos usar então a **raiz da distância quadrática média** (Ou distância RMS, o mesmo método que usamos para definir o [[Valor Eficaz ou RMS|valor eficaz da tensão e corrente AC]]) isto é:

$$
D_{rms} = \sqrt{\langle D_N^2 \rangle} = \sqrt{N}
$$

Digamos agora que adicionamos mais uma complicação ao nosso problema, visando o tornar mais parecido com a nossa ideia para o movimento térmico das partículas, temos então um passo que ao invés de ser sempre igual a $1$ será quase sempre $1$ mas oscilará imprevisivelmente entre os valores próximos a $1$, isto é, cada passo terá um comprimento $S$ ou um comprimento médio $\langle S^2 \rangle = 1$, nesse caso, qual seria a possibilidade do jogador estar a  uma distância qualquer $X$ após $N$ passos? 

A resposta será $0$ para qualquer valor de $X$, antes, estávamos falando de valores discretos para a posição, a distância do jogador com relação a origem era sempre um valor inteiro o que já não é mais verdades, a distância ocupa agora intervalos contínuos e então a probabilidade do jogador estar num valor exato $X$ é infinitesimal (essa é, em termos de probabilidade e estatística, a transição de [[Variável Aleatória Discreta]] para [[Variável Aleatória Contínua]]), precisamos então considerar agora a probabilidade não mais de pontos específicos, mas de intervalos, nesse caso, a probabilidade do jogador estar a uma distância entre $x_a$ e $x_b$ é:

$$
P(x_a \leq D \leq x_b) = \int_{x_a}^{x_b} p(x)dx
$$

Onde $p(x)$ é a distribuição de probabilidade que modela o problema, que nesse caso é a [[Distribuição Normal]].

Essa mesma ideia de probabilidade serve para muitas outras questões na física e o problema do caminho aleatório é o primeiro passo para entender isso, é conveniente por exemplo falar da velocidade das moléculas para pensar em questões como a temperatura, porém, não temos como medir a velocidade de cada átomo individualmente e cada átomo pode ter uma velocidade diferente, trabalhamos então com conceitos de probabilidade. 

Uma molécula específica pode ter qualquer velocidade, mas algumas são mais prováveis, então esperamos que em média exista um valor mais comum para as velocidades, um valor esperado $\langle v\rangle$ e que a probabilidade de uma partícula arbitrária ter uma velocidade entre $v$ e $v + \Delta v$ é dada por uma função densidade de probabilidade $p(v)\Delta v$, função essa que de fato existe e cuja forma foi encontrada por Maxwell.


Uma outra maneira de pensar é que num recipiente com um grande numero de átomos $N$ o valor esperado de moléculas com velocidade entre $v$ e $v+\Delta v$ é então dada por

$$
\langle N\rangle = Np(v)\Delta v
$$

E como para uma situação real $N \approx 10^{22}$, frequentemente ocultamos o termo "valor esperado" e simplesmente assumimos que existem $N$ partículas nessa faixa de velocidade, mas devemos sempre ter noção que essa ideia continuam sendo considerações probabilísticas.