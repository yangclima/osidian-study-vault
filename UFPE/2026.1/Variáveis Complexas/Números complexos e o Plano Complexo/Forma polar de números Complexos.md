Como já vimos, podemos usar indiscriminadamente a terminologia de ponto para designar [[Números Complexos]], isto é, considerar um número qualquer $z = x + iy$, como um ponto $(x,y)$ no [[O plano complexo|plano complexo]], dessa maneira, podemos aplicar aqui a ideia das coordenadas polares, denotando um ponto qualquer do plano complexo, ou seja, um número complexo $z$ qualquer através de um par de coordenadas $(r,\theta)$, onde $r$ é a distância do ponto à origem do sistema de coordenadas e $\theta$ o ângulo que o vetor posição do ponto faz com o eixo $x$, também chamado de **argumento de z**.

Temos então, para um ponto $z = x+iy$:

$$
\begin{cases}
x= r\cos(\theta) \\
y= r\sin(\theta)
\end{cases} \ \ \ \ \ \ \ \ \ \ \
\begin{cases}
r = |z| = \sqrt{x^2 + y^2} \\
\theta = \arg{(z)} =  \arctan(y/x)
\end{cases}
$$

De tal forma que:

$$z = x+iy = r(\cos{\theta} + i\sin{\theta})$$

E dizemos que esta é a **representação polar** do número complexo $z$.

Algo a se notar é que devido a periodicidade das funções trigonométricas, o argumento de $z$ é na verdade um conjunto de valores, uma vez que seja $\arg(z) = \theta_0$, o valor $\theta_0 \pm n\cdot 2\pi$ designa o mesmo ângulo e portanto pode ser tomado como o argumento de $z$, para eliminar então essa ambiguidade, definimos o valor $\text{Arg}(z) = \arg(z) + 2n\pi, \ \ \ n = 0, \pm 1,\pm 2,\pm 3$ , que pertence sempre ao intervalo $(-\pi, \pi)$, e portanto tem um valor único.

Essa representação é especialmente útil ao realizar [[Aritmética de números complexos|multiplicação e divisão]], onde sendo $z_1 = r_1(\cos \theta_1 + i\sin\theta_1)$ e $z_2 = r_2(\cos \theta_2 + i\sin\theta_2)$vale que:


$$\text{}z_1z_2 = r_1r_2(\cos (\theta_1 + \theta_2) + i\sin(\theta_1 + \theta_2))$$

$$\frac{z_1}{z_2} = \frac{r_1}{r_2}(\cos (\theta_1 - \theta_2) + i\sin(\theta_1 - \theta_2))$$

$$
z_1^n = r_1^n(\cos{(n\cdot\theta_1)} + \sin{(n\cdot\theta_1)}), n \in \mathbb{N}
$$


Um resultado interessante é a chamada **Fórmula de De Moivre** que, para o caso em que $|z| = 1 = \cos\theta + i\sin\theta$ vale que:

$$z^n = cos(n\theta) - i\sin(n\theta)$$
