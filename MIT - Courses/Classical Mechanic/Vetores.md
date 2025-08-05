Algumas quantidades físicas podem ser mensuradas apenas através de escaleres, ou seja, quantidades numéricas acompanhadas  das devidas unidades, por outro lado, não faz sentido pensar em grandezas tais como a força, a posição, a velocidade apenas como escalares, nós aplicamos um força em uma direção específica, um objeto está numa posição relativa a algo e se move numa direção específica, assim, grandezas físicas como estas, precisam de uma representação que tenham tanto magnitude quanto direção, essa é a **Representação vetorial**. Tendo isso em vista, podemos definir um vetor da seguinte forma:

> Uma quantidade que tem tanto direção quanto magnitude

Vetores normalmente são representados através da notação $\vec{v}$, enquanto sua magnitude é descrita por $|\vec{v}|$.

Podemos operar sobre estas quantidades de diferentes formas, as operações básicas são a **adição de vetores** e a **multiplicação entre vetores e escalares** que são a base para a definição dos chamados [[Espaços vetoriais]].
# Adição de vetores
$$
\vec{a} = \vec{b} + \vec{c}
$$
A adição de vetores tem as seguintes propriedades:
1. Comutatividade: $\vec{a} + \vec{b} = \vec{b} + \vec{a}$
2. Associatividade: $\vec{a} + (\vec{b} + \vec{c}) = (\vec{a} + \vec{b}) + \vec{c}$
3. Existência de elemento neutro (Identidade): $\vec{0} + \vec{a} = \vec{a}$
4. Existência de elemento inverso: $\vec{a} + (-\vec{a}) = \vec{0}$
# Multiplicação de vetores por escalares
$$
\vec{a} = k \vec{b}
$$
A multiplicação de um vetor por um escalar tem as seguintes propriedades:
1. Associativa: $b(c \vec{a}) = (bc)\vec{a}$
2. Distributiva com relação a adição de vetores: $k(\vec{a} + \vec{b}) = k\vec{a} + k\vec{b}$
3. Distributiva com relação a adição de escalares: $(c + b)\vec{a} = c\vec{a} + b\vec{a}$
4. Existência de elemento neutro: $1 \vec{a} = \vec{a}$
# Vetor unitário
Para alguns cálculos e aplicações dos vetores é útil descrevê-los como combinações de outros vetores, para isso, usamos principalmente os vetores unitários. Um vetor unitário $\hat{v}$ é uma versão do vetor $\vec{v}$ que possui a mesma direção que ele porém, magnitude unitária, ou seja $|\hat{v}| = 1$, o vetor unitário pode ser calculado da seguinte forma:
$$
\hat{v} = \dfrac{\vec{v}}{|\vec{v}|}
$$
Ou seja, o quociente de do vetor pela sua magnitude.
# Sistemas de coordenadas
Para ilustrar os fenômenos físicos e nesse objetivo, utilizar os vetores, é de extrema importância definirmos **quadros de referência**, ou **referenciais**, para resolver os nosso problemas de física, parar isso, utilizamos os **sistemas de coordenadas**.Os mais comuns sistemas de coordenadas são o [[O plano coordenado|Sistema de coordenados cartesianas]] e o sistemas de coordenadas cilíndricas. Para definir o sistema de coordenadas mais convenientes para um problema específico seguimos a seguinte ordem:
1. Definir uma origem
2. Definir os eixos coordenados
3. Definir a direção positiva para cada eixo
4. Definir os vetores unitários para cada ponto no espaço
## Sistema de coordenadas cartesianas 
1. Primeiro definimos a origem $O$ no local mais conveniente possível para a resolução do problema.
2. Definimos os eixos coordenados $x$, $y$ e $z$ com ângulos retos entre si e se intersectando na origem $O$.
3. Definimos as direções positivas de cada eixo, normalmente através de uma cabeça de seta ou com os símbolos $+x$, $+y$ e $+z$.
4. Definimos os vetores unitários $\hat{i}$, $\hat{j}$ e $\hat{k}$, apontando respectivamente na direção dos eixos $x$, $y$ e $z$, sendo iguais para qualquer ponto $P$ no espaço.
Seguindo esses passos, construímos um sistema de coordenadas em que podemos representar um ponto $P$ qualquer no espaço através de suas coordenadas relativas a cada eixo do sistema, ou seja, $P = (x, y, z)$.
## Sistema de coordenadas cilíndricas
1. Primeiro definimos a origem $O$ no local mais conveniente possível para a resolução do problema, normalmente esse sistema de coordenadas é usado para resolver problemas relacionados a corpos em rotação, e nesses problemas, normalmente o ponto mais conveniente para definirmos como origem é o eixo de rotação.
2. Os eixos seguem a mesma lógica do sistema cartesiano, são 3 eixos coordenados $x$, $y$ e $z$ com ângulos retos entre si se intersectando na origem.
3. Definimos as direções positivas de cada eixo, da mesma forma que no sistema de coordenadas cartesianas.
4. Definimos os vetores unitários $\hat{r}$, $\hat{\theta}$ e $\hat{k}$, sendo que $\hat{r}$ aponta na direção da distância entre o eixo $z$ e o ponto em questão, $\hat{\theta}$ aponta na direção perpendicular a $\hat{r}$ e $\hat{k}$ apontas direção do eixo $z$, perceba que os vetores unitários mudam de direção a depender do ponto.
Dessa forma, representamos qualquer ponto nesse sistema de coordenadas através de 3 variáveis: A distância $r$ do ponto para o eixo $z$, o ângulo $\theta$ formado entre o segmento $OD$ e o eixo $x$ positivo ($\theta$ é positivo caso seja mensurado no sentido anti-horário e negativo caso contrário), onde $D$ é a projeção ortogonal do ponto no plano $xy$, e $z$ é coordenada familiar do ponto no eixo $z$, sendo assim  $P=(r, \theta, z)$.
### Coordenadas polares
Quando eliminamos o eixo $z$, ainda podemos usar as coordenadas $r$ e $\theta$ para designar qualquer ponto no plano $xy$, essa coordenadas são chamadas de **coordenadas polares**, é possível utilizar isso para a resolução de diversos problemas, transformando coordenadas cartesianas de um ponto ou vetor em coordenadas polares e vice-versa, essa transformações são dadas por:
$$
(x,y) = 
\begin{cases}
	x = r\cos{\theta} \\
	y = r\sin{\theta}
\end{cases}
$$
(Para converter de polares para cartesianas) Ou seja:
$$
(x, y) = (r\cos{\theta}, r\sin{\theta})
$$
Ou (Para converter de cartesianas para polares):
$$
(r, \theta) = 
\begin{cases}
	r = + \sqrt{x^2 + y^2} \\
	\theta = \tan^{-1}{\dfrac{y}{x}}
\end{cases}
$$
Ou seja:
$$
(r, \theta) = (\sqrt{x^2 + y^2}, \tan^{-1}{\dfrac{y}{x}})
$$
Os vetores unitários, por sua vez, podem ser transformados da seguinte maneira:
$$
\begin{cases}
\hat{r} = \cos{(\theta)} \hat{i} + \sin{(\theta)} \hat{j} \\
\hat{\theta} = - \sin{(\theta)} \hat{i} + \cos{(\theta)} \hat{j}  
\end{cases}
\ \ \ \ \text{e} \ \ \ \
\begin{cases}
\hat{i} = \cos{(\theta)} \hat{r} - \sin{(\theta)} \hat{r} \\
\hat{j} = - \sin{(\theta)} \hat{r} + \cos{(\theta)} \hat{\theta}  
\end{cases}
$$

