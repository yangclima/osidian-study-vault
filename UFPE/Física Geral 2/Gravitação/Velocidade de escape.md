---
aula: 3
---
Newton, ao formular a sua teoria acerca da [[Força Gravitacional]] ele constatou que era possível utilizá-la para explicar o movimento dos corpos celestes, utilizando para explicar seu ponto a analogia de um canhão disparando bolas de canhão cada vez mais forte ao horizonte até que elas entram em órbita

![[valocidade_de_escape01.png|center]]

O interessante é que existe uma velocidade fixa que independente da massa permite que ele escape da gravidade da terra, ela pode ser obtida seguinte maneira:
$$
\lim_{r \rightarrow \infty} K_i + U_i = \lim_{r \rightarrow \infty} K_f - U_f
$$
$$
 \dfrac{mv^2}{2} + (-\dfrac{GMm}{r_i}) = \lim_{r_f \rightarrow \infty} \dfrac{mv^2}{2} + (-\dfrac{GMm}{r_f})
$$
Como em $r_f$ tendendo a infinito a [[Energia Potencial Gravitacional]] é 0 e ao modelar o conceito de velocidade de escape definimos que a velocidade final é 0, temos:
$$
 \dfrac{mv^2}{2} + (-\dfrac{GMm}{r_i}) = \lim_{r_f \rightarrow \infty} \cancel{\dfrac{mv^2}{2}} + \cancel{(-\dfrac{GMm}{r_f})}
$$
$$
 \dfrac{\cancel{m}v^2}{2} = \dfrac{GM\cancel{m}}{r_i} \implies  \dfrac{v^2}{2} = \dfrac{GM}{r_i} \implies v = \sqrt{\dfrac{2GM}{r_i}}
$$
Como $r_i$ é a superfície do planeta temos o seguinte:
$$
v_{esc} = \sqrt{\dfrac{2GM}{R}}
$$