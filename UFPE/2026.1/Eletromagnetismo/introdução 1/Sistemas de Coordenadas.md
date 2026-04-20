Em geral, no eletromagnetismo, as quantidades físicas com as quais lidaremos são funções do espaço e do tempo, nesse sentido, torna-se essencial possuir alguma ferramenta que permita distinguir de maneira unívoca todos os pontos do espaço.

Essa distinção pode ser feita através de um sistema de coordenadas, seja ele ortogonal (Sistema de coordenadas no qual as coordenadas são mutuamente perpendiculares) ou não-ortogonal, sendo esses últimos de pouca ou nenhuma utilidade no eletromagnetismo.

Veremos então os três mais úteis sistemas de coordenadas: Cartesiano, Cilíndrico e Esférico.
# Sistema de Coordenadas Cartesianas
No sistema cartesiano um ponto $P$ qualquer do espaço pode ser descrito através de uma tripla de coordenas $(x,y,z)$ onde cada uma das coordenadas referencia o ponto com relação a um dos eixos coordenados e todas tem intervalo de variação de $(-\infty,\infty)$.

Um vetor, por sua vez, pode ser escrito como:

$$(A_x, A_y, A_z) = A_x{\vec a_x} + A_y{\vec a_y} + A_z{\vec a_z}$$

Onde $\vec a_x$, $\vec a_y$ e $\vec a_z$, são vetores unitários ao longo dos eixos $x$, $y$ e $z$, respectivamente.
# Sistema de Coordenadas Cilíndricas
No sistemas de coordenadas cilíndricas, conveniente quando tratamos de problemas com simetria cilíndrica, um ponto $P$ é representado por $(\rho, \phi,z)$, onde $\rho$, limitado ao intervalo $[0,\infty)$ representa a distância radial do ponto com relação ao eixo $z$, $\phi$, limitado ao intervalo $[0,2\pi]$ representa o ângulo azimutal, medido com relação ao $x$ no plano $xy$ e $z$, limitado ao intervalo $(-\infty, \infty)$, representa a posição do ponto no eixo $z$.

Da mesma forma, representamos um vetor $A$ nesse sistema como:

$$(A_\rho, A_\phi, A_z) = A_\rho\vec a_\rho + A_\phi\vec a_\phi +  A_z\vec a_z$$

Onde $\vec a_\rho$, $\vec a_\phi$ e $\vec a_z$ são vetores unitários ao longo de $\rho$, $\phi$ e $z$, respectivamente.

E para converter entre esse sistema e o cartesiano podemos usar:

| Cilíndricas | Cartesianas        |
| ----------- | ------------------ |
| $\rho$      | $\sqrt{x^2 + y^2}$ |
| $\phi$      | $\arctan(y/x)$     |
| $z$         | $z$                |

Ou para fazer o contrário:

| Cartesianas | Cilíndricas       |
| ----------- | ----------------- |
| $x$         | $\rho \cos(\phi)$ |
| $y$         | $\rho \sin(\phi)$ |
| $z$         | $z$               |

Além disso, para permutar  os vetores unitários entre esses sistemas, usamos:

| Cilíndricas   | Cartesianas                                |
| ------------- | ------------------------------------------ |
| $\vec a_\rho$ | $\cos(\phi)\vec a_x + \sin(\phi)\vec a_y$  |
| $\vec a_\phi$ | $-\sin(\phi)\vec a_x + \cos(\phi)\vec a_y$ |
| $\vec a_z$    | $\vec a_z$                                 |

Ou, de forma similar

| Cartesianas | Cilíndricas                                     |
| ----------- | ----------------------------------------------- |
| $\vec a_x$  | $\cos(\phi)\vec a_\rho - \sin(\phi)\vec a_\phi$ |
| $\vec a_y$  | $\sin(\phi)\vec a_\rho + \cos(\phi)\vec a_\phi$ |
| $\vec a_z$  | $\vec a_z$                                      |
# Sistema de Coordenadas Esféricas
No sistema de coordenadas esféricas, muito útil ao lidar com problemas de simetria esférica, representamos cada ponto $P$ no espaço através de um tripla de coordenadas $(r, \theta, \phi)$ onde $r$, limitado ao intervalo $(-\infty, \infty)$ representa a distância do ponto com relação a origem do sistema de coordenadas, $\theta$ é o ângulo denominado co-latitude, é limitado ao intervalo $[0,\pi]$ e representa o ângulo do vetor posição de $P$ com relação ao eixo $z$ e, por fim, $\phi$, limitado ao intervalo $[0,2\pi]$, representa, assim como nas coordenadas cilíndricas o ângulo azimutal medido com relação ao eixo $x$ no plano $xy$.

Um vetor $A$, nesse sistema, pode então ser representado por:

$$(r,\theta,\phi) = A_r\vec a_r + A_\theta \vec a_\theta + A_\phi \vec a_\phi$$

Onde os vetores $\vec a_r$, $\vec a_\theta$ e $\vec a_\phi$ são vetores unitários ao longo de $r$, $\theta$ e $\phi$, respectivamente.

Para relacionar essas coordenadas com as coordenadas cartesianas, usamos:

| Esféricas | Cartesianas                                         |
| --------- | --------------------------------------------------- |
| $r$       | $\sqrt{x^2+y^2+z^2}$                                |
| $\theta$  | $\arctan{\left(\dfrac{\sqrt{x^2+y^2}}{z^2}\right)}$ |
| $\phi$    | $\arctan(y/x)$                                      |

Ou, de forma inversa:

| Esféricas | Cartesianas               |
| --------- | ------------------------- |
| $x$       | $r\sin(\theta)\cos(\phi)$ |
| $y$       | $r\sin(\theta)\sin(\phi)$ |
| $z$       | $r\cos(\theta)$           |
|           |                           |

Finalmente, para relacionar os vetores unitários dos dois sistemas, usamos as seguintes relações:

| Esféricas       | Cartesianas                                                                              |
| --------------- | ---------------------------------------------------------------------------------------- |
| $\vec a_r$      | $\sin(\theta)\cos(\phi)\vec a_x + \sin(\theta)\sin(\phi)\vec a_y + \cos(\theta)\vec a_z$ |
| $\vec a_\theta$ | $\cos(\theta)\cos(\phi)\vec a_x + \cos(\theta)\sin(\phi)\vec a_y - \sin(\theta)\vec a_z$ |
| $\vec a_\phi$   | $-\sin(\phi)\vec a_x + \cos(\phi)\vec a_y$                                               |

Ou,  de forma inversa:

| Cartesianas | Esféricas                                                                                        |
| ----------- | ------------------------------------------------------------------------------------------------ |
| $\vec a_x$  | $\sin(\theta)\cos(\phi)\vec a_r + \cos(\theta)\cos(\phi)\vec a_\theta - \sin(\theta)\vec a_\phi$ |
| $\vec a_y$  | $\sin(\theta)\sin(\phi)\vec a_r + \cos(\theta)\sin(\phi)\vec a_\theta + \cos(\phi)\vec a_\phi$   |
| $\vec a_z$  | $\cos(\theta) a_r - \sin(\theta)\vec a_\theta$                                                   |

