A cinemática é área da física que tem como objetivo descrever matematicamente o movimento dos corpos, sobretudo a partir das grandezas vetoriais de posição, velocidade e aceleração.
# Referencial
O movimento só pode ser pensado definindo um referencial, ou seja, pensando no movimento como a mudança da distância entre o corpo em questão e algum outro corpo ou ponto do espaço. O referencial descreve portanto o tempo e o espaço em que pretendemos calcular algum grandeza ou propriedade física, normalmente usamos [[Vetores#Sistemas de coordenadas|sistemas de coordenadas]] para localizar corpos no nosso referencial.
# Posição
A posição de um corpo é uma grandeza vetorial normalmente denotada por $\vec{r}$, um vetor que representa a posição do corpo no referencial em questão, se o objeto está se movendo, num movimento unidimensional, podemos definir sua posição como uma função do tempo, portanto:
$$
\vec{r}(t) = x(t) \ \hat{i}
$$
A unidade de medida no S.I para a posição é o metro ($m$).
# Intervalo de tempo
Um intervalo de tempo é um intervalo fechado entre dois instantes distintos no tempo $[t_i, t_f]$ e normalmente são representados, usando [[Notação Delta]], por $\Delta t$ onde $\Delta t = t_f - t_i$ e representa a quantidade de tempo entre os dois instantes. No S.I. a unidade de medida de tempo é o segundo ($s$).
# Deslocamento
O deslocamento de um corpo é definido como a mudança na sua posição ocorrida durante um determinado espaço de tempo, ou seja, a variação do vetor posição num determinado espaço de tempo. O deslocamento é representado da seguinte forma:
$$
\Delta \vec{r} = \vec{r}(t_f) - \vec{r}(t_i) = (x(t_f) - x(t_i))\hat{i} = \Delta x (t) \hat{i}
$$
# Velocidade
## Velocidade média 
A velocidade média de um corpo no espaço é definida como  o quociente entre seu deslocamento e o intervalo de tempo no qual esse deslocamento ocorreu, ou seja:
$$
\vec{v}_{méd} = \dfrac{\Delta x}{\Delta t} \hat{i}
$$
## Velocidade instantânea
A velocidade instantânea é o deslocamento do corpo num intervalo infinitesimal, ou seja, com $t \rightarrow 0$, sendo assim, a [[Derivada]] da sua posição no tempo:
$$
\vec{v}_{inst} = \dfrac{d}{dt}x(t) \hat{i}
$$
# Aceleração
## Aceleração média
A aceleração média de um corpo no espaço é definida como  o quociente entre a variação da sua velocidade e o intervalo de tempo no qual essa variação ocorreu, ou seja: 
$$
\vec{a}_{méd} =  \dfrac{\Delta v}{\Delta t}
$$
## Aceleração instantânea
A aceleração instantânea é definida como o variação da velocidade num instante de tempo infinitesimal, ou seja, a derivada da velocidade em função do tempo:
$$
\vec{a}_{inst} = \dfrac{d}{dt}v(t) \hat{i}
$$
# Cinemática e integração
Como vimos, podemos descobrir a velocidade e aceleração de um corpo apenas usando sua função de posição o tempo e conhecendo o processo da [[Derivada]], porém, sabemos também que a [[Integral Indefinida]] é o processo inverso da derivada e portanto podemos definir a velocidade e a posição do corpo apenas conhecendo sua aceleração a partir de:
$$
\vec{v}(t) = \int a(t)dt \ \hat{i}
$$
$$
\vec{r}(t) = \int v(t)dt \ \hat{i}
$$
E caso não tenhamos informações explícitas dessa função podemos podemos utilizar nosso conhecimentos sobre o [[Integral definida|problema da área]] para interpretar a velocidade como a área abaixo do gráfico de $a(t)$ e o deslocamento como a área abaixo do gráfico de $v(t)$ , definindo inclusive, sua variações definidas num intervalo $[a, b]$ através dos limites de integração, ou seja:
$$
\Delta \vec{v}(t) = \int_a^b a(t)dt \ \hat{i}
$$
$$
\Delta \vec{r}(t) = \int_a^b v(t)dt \ \hat{i}
$$
