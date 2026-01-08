Nosso objetivo é expandir a nossa atual é expandir a nossa definição da [[Lei da Probabilidade Total]] para abranger distribuições contínuas de probabilidade.

Suponha que temos um parâmetro $\theta$ continuamente distribuído, isto é, uma [[Variável Aleatória Contínua]] no intervalo $[a, b]$ e um dado aleatório discreto $x$, assumindo que $\theta$ seja por si só, aleatório e siga uma função densidade de probabilidade $f(\theta)$ e que $x$ e $\theta$ tem verossimilhança $p(x|\theta)$, então a **probabilidade total de $x$** ou **probabilidade preditiva a priori de $x$** é dada por:

$$
p(x) = \int_a^b p(x|\theta)f(\theta)d\theta
$$

Perceba que estamos encarando a mesma lei da probabilidade total, mas é como se aqui tivéssemos lidando com uma partição infinita onde $f(\theta)d\theta$ é a probabilidade de cada partição.