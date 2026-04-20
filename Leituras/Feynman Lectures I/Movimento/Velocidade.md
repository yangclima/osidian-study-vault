Uma vez estabelecido o conceito de **posição**, o próximo passo natural no estudo da Cinemática é introduzir a noção de **velocidade**, que descreve a rapidez e o sentido com que a posição de um corpo varia ao longo do tempo.

No cotidiano, o termo “velocidade” é usado de forma intuitiva para indicar quão rápido um objeto se move. No entanto, essa noção informal não é suficiente para uma descrição física rigorosa, pois não especifica **como** a posição do corpo varia nem **em que intervalo de tempo** essa variação ocorre.

Considere um objeto que ocupa a posição $s = s(t)$ em um movimento unidimensional. Se, durante um intervalo de tempo $\Delta t = t_f - t_i$, a posição do corpo varia de $s(t_i)$ para $s(t_f)$, definimos a **velocidade média** nesse intervalo como

$$
v_m = \frac {\Delta s} {\Delta t} = \frac{s(t_i) - s(t_f)}{t_f - t_i}
$$

A velocidade média fornece uma descrição global do movimento durante o intervalo considerado, mas **não caracteriza o comportamento do corpo em um instante específico**. Dois movimentos muito diferentes podem apresentar a mesma velocidade média (Imagine um carro que percorre $50 \ km$ em uma hora e depois pare por mais uma hora e um outro que percorre $50 \ km$ se movendo a uma velocidade constante durante duas horas, nesse intervalo de tempo de duas horas, ambos os carros tiveram a mesma velocidade média apesar de sabermos que o primeiro percorreu sua trajetória muito mais rápido).

Na prática, é comum afirmar que um automóvel “está a 100 km/h”. Essa afirmação não significa que o veículo percorreu exatamente 100 km em uma hora, mas sim que, naquele instante, sua velocidade apresenta esse valor.

Durante o intervalo de uma hora, a velocidade do automóvel pode variar continuamente, de modo que a velocidade média nesse intervalo pode diferir do valor indicado no velocímetro. Torna-se, portanto, necessário definir uma grandeza que descreva o movimento **em um instante de tempo**, e não apenas em intervalos finitos.

Para resolver esse problema, precisamos então pensar na velocidade de forma instantânea. Ao invés do espaço percorrido em um intervalo de tempo precisamos que a velocidade seja uma característica e tenha um valor bem definido para um instante do tempo $t$, para isso, podemos considerar um $\Delta t$ cada vez menor, como se estivéssemos tornando-o um intervalo tão curto que no limite a velocidade naquele intervalo seria igual a velocidade no instante $t$, isto é, pegar uma distância percorrida infinitesimal, um tempo infinitesimal correspondente, e avaliar a razão do dois quando o o tempo se torna cada vez menor, se aproximando de zero.

Essa é uma das ideias mais importante da física e envolveu o desenvolvimento de uma das grandes áreas da matemática: o [[Single Variable Calculus|cálculo diferencial]], idealizado de forma independente e simultânea por *Isaac Newton* e *Gottfried Leibniz*.

Com o devido rigor matemático, para definir a velocidade, a ideia é então pegar um deslocamento (Ou variação na posição) $\Delta s$ e um intervalo de tempo $\Delta t$ e tomar o [[Limite]] quando esse intervalo de tempo tende a zero, ou seja:

$$
v =  \lim_{\Delta t \to 0} \frac{\Delta s}{\Delta t}
$$

Como esse processo e ideia são muito comuns na matemática e na física foi desenvolvida uma série de notações para lidar com situações como essa, por exemplo:

$$
v =  \lim_{\Delta t \to 0} \frac{\Delta s}{\Delta t} = \frac{ds}{dt}
$$

A quantidade $ds/dt$ é o que chamamos de **[[Derivada|derivada]] de $s$ em relação a $t$** e o processo através do qual a obtemos é chamado de derivação ou diferenciação enquanto os termos $ds$ e $dt$ são chamados de diferenciais

Já vimos porém que a posição é idealmente descrita por uma equação horária da posição, uma função em $t$, isto é $s = f(t)$, nesse caso, $\Delta s = f(t + \Delta t) - f(t)$ e então:

$$
v = v(t) = \lim_{\Delta t\to 0} \frac{s(t + \Delta t) - s(t)}{\Delta t} = \frac{d}{dt}s(t) = s^\prime(t)
$$

Assim, obtemos que por definição, **a velocidade é definida como a derivada temporal da nossa função posição no tempo**, também podendo ser compreendida com a taxa de variação instantânea da posição no tempo, o que faz sentido, afinal, quanto maior a velocidade, mais "brusca" é a variação da posição.

Além disso, sabemos que como para um intervalo infinitesimal de tempo $dt$ a velocidade $v$ é bem definida e constante e a sua posição varia $ds$ nesse intervalo, podemos dizer que $ds = v(t)\cdot dt$ e então, conhecendo a velocidade, isto é, a função em $t$ que corresponde à velocidade instantânea do objeto, poderíamos somar os pedacinhos $ds$ obtendo o deslocamento do objeto num intervalo finito de tempo, ou seja:

$$
\Delta s = \sum ds = \sum v(t)dt
$$

Entretanto esse é um tipo especial de somatório, afinal, estamos somando pedaços infinitesimais e portanto infinitos pedaços para compor um pedaço finito, essa é uma outra ideia do cálculo diferencial e se chama de integral:

$$
\Delta s = \int_{t_i}^{t_f} v(t)dt \implies s(t) = \int v(t)dt
$$

Ou seja, por definição, a função horária da posição é a integral da função velocidade no tempo e existe uma relação de reciprocidade entre a derivação e a integração.