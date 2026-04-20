Um dos mais importantes conceitos que aprenderemos sobre os [[Números Complexos]] são as definições a respeito de funções de números complexos, antes disso, porém, precisaremos ter em mente alguns conceitos e terminologias sobre conjuntos de pontos no [[O plano complexo|plano complexo]].

Consideremos os pontos $z_0 = x_0 + iy_0$ e $z = x + iy$ no plano complexo. Como $|z - z_0|$ representa a distância $\sqrt{(x-x_0)^2 + (y-y_0)^2}$ entre esses pontos, a equação

$$|z-z_0| = \rho\,; \ \ \rho > 0$$

É satisfeita apenas pelos pontos que estão a uma distância $\rho$ de $z_0$, portanto, uma circunferência de raio $\rho$ centrada em $z_0$.

De forma similar, se considerarmos os mesmo pontos mas utilizarmos a equação a seguir

$$|z-z_0| \leq \rho\,; \ \ \rho > 0$$

Estaremos designando todos os pontos $z$ que estão a uma distância menor que $\rho$ do ponto $z_0$, portanto, um disco de raio $\rho$ e centrado em $z_0$, por outro lado, se utilizarmos a desigualdade restrita escrevendo

$$|z-z_0| < \rho\,; \ \ \rho > 0$$

estaremos designando todos os pontos que estão no interior desse disco, isto é, pertencem a ele mas não estão em sua fronteira (A circunferência de raio $\rho$ centrada em $z_0$), nesse caso, chamamos esse conjunto de pontos de **vizinhança de $z_0$**, ou, sendo ainda mais específico e removendo do conjunto o ponto $z_0$ utilizando a equação

$$0 < |z-z_0| < \rho\,; \ \ \rho > 0$$

temos a chamada **vizinhança deletada de $z_0$**. 

A partir disso, dizemos que um  ponto qualquer $z_0$ é um **ponto interior** de um conjunto qualquer $S$ de pontos no plano complexo se existir alguma vizinhança de $z_0$ inteiramente contida em $S$, além disso, definimos um conjunto arbitrário $S$ como um **conjunto aberto** se e somente se, todos os pontos que a ele pertencem forem pontos internos, ou de maneira menos formal, se ele não tiver fronteira.

Nesse mesmo sentido, se todas as vizinhanças de um ponto $z_0 \in S$ contiver pelo menos um ponto que está em $S$ e um ponto que não está, dizemos que $z_0$ é um **ponto de fronteira** de $S$, e a coleção de pontos de fronteira de $S$ é então definida formalmente como sua fronteira.

Assim, todo ponto $z$ que não é ponto interior nem ponto de fronteira de um conjunto de pontos $S$ (Existir pelo menos uma fronteira de $z$ que não contém nenhum ponto de $S$) é denominado **ponto exterior** de $S$.

Uma outra região notável no plano complexo é um anel, formada pelo conjunto de todos os pontos $z$ que estão a uma distância maior que o raio interno $\rho_1$ do anel mas a uma distância menor que o raio externo $\rho_2$ do anel com relação ao seu centro $z_0$, região matematicamente descrita por:

$$ \rho_1 < |z-z_0| < \rho_2\,; \ \ \rho_1,\rho_2 > 0$$

Como as desigualdades são estritas esse é o anel denominado anel aberto, enquanto o anel fechado poderia ser descrito por 

$$ \rho_1 \leq |z-z_0| \leq \rho_2\,; \ \ \rho_1,\rho_2 > 0$$

Uma outra definição essencial é que dado um conjunto qualquer de pontos $S$ no plano complexo, se quaisquer dois pontos $z_1,z_2 \in S$ puderem ser conectados por uma linha poligonal composta apenas por segmentos de reta inteiramente contidos em no conjunto, dizemos que $S$ é um conjunto conexo.

Unindo então as definições, todo conjunto de pontos $S$ simultaneamente aberto e conexo é denominado **Domínio** e um domínio juntamente com todos, alguns ou nenhum de seus pontos de fronteira é denominado **Região**.

Uma observação importante é que um conjunto $S$, pode não ser nem aberto nem fechado, basta que ele possua uma fronteira que não o envolva completamente.

Por fim, dizemos que um conjunto $S$ é **Limitado**, se e somente se existir um número $R > 0$ tal que $\forall z \in S, |z| < R$, ou seja, se existir um valor de $R > 0$ tal que o conjunto $S$ esteja inteiramente contido em um disco de raio $R$ centrado na origem, se essa condição não for satisfeita, dizemos que $S$ é um conjunto ilimitado

