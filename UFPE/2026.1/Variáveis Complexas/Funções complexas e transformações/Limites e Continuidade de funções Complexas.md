Assim como temos a definição de [[Limite]] de uma [[Função]] real, podemos definir o limite de [[Funções Complexas]]:

> Seja $f$ uma função complexa definida em uma vizinhança de $z_0$ e seja uma número $L$ um [[Números Complexos|número complexo]]. O limite de $f$ à medida que $z$ tende a $z_0$ existe e é igual a $L$, o que é representado como $\lim\limits_{z\to z_0} f(z) = L$, se, para todo $\varepsilon > 0$, existir algum $\delta > 0$ tal que $|f(z) - L| < \varepsilon$ sempre que $0 < |z - z_0| < \delta$.

Essa definição se assemelha a definição de [[Limite e Continuidade de funções de mais de uma variável]], e pode ser interpretada da seguinte maneira: O limite existe se e somente se existe uma [[Conjuntos de pontos no plano complexo|vizinhança deletada]] de $z_0$ de raio $\delta$ tal que para todos os pontos $z$ desta vizinhança, $f(z)$ pertence a vizinhança $\varepsilon$ de $L$, isto é, se todos os pontos dessa vizinhança deletada são mapeados por $f$ em uma vizinhança de raio $\varepsilon$ de $L$.

A principal semelhança com os limites de funções de múltiplas variáveis é que, diferente do que se tem para os limites de funções de uma única variável onde o limite existe se e somente se os [[Limites Laterais]] são iguais, aqui, existem infinitas direções de aproximação de $z \to z_0$ e é suficiente que apenas duas dessas direções levem a dois limites diferentes para implicar na inexistência do limite, o que estabelece o seguinte critério:

> Se $f$ se aproximar de dois [[Números Complexos]] $L_1 \neq L_2$ ao longo de duas curvas ou percursos diferentes que passam por $z_0$, então $\lim\limits_{z\to z_0}f(z)$ não existe.

Apesar dessa ser a definição do limite de números complexos ela não nos ajuda muito a calcular os limites dessa funções, existe porém uma definição que relaciona o limite complexo de $f(z) = u(x,y) + v(x,y)i$ com os limites das funções reais $u$ e $v$.

> Sejam $f(x,y) = u(x,y) + iv(x,y)$, $z_0 = x_0 + iy_0$ e $L = u_0 + iv_0$, então o limite denotado por $\lim\limits_{z\to z_0} f(z) = L$ se e somente se
>  $$\lim\limits_{(x,y)\to (x_0,y_0)} u(x,y) = u_0 \ \ \ \ \ \ \ \ \ \ \text{e} \ \ \ \ \ \ \ \ \ \ \lim\limits_{(x,y)\to (x_0,y_0)} v(x,y) = v_0$$


Assim, valem todas as propriedades dos limites de funções de múltiplas variáveis para os limites de variáveis complexas.

Agora que definimos o conceito de limite de variáveis complexas, temos todas as ferramentas necessárias para definir a continuidade de uma função complexa através da seguinte definição:

> Uma função complexa é **contínua** em um ponto $z_0$ do [[O plano complexo|plano complexo]] se 
> $$\lim\limits_{z\to z_0} f(z) = f(z_0)$$
> O que equivale ao fato de que a continuidade de $f(z)$ depende da existência de seu limite em $z_0$, de que $f$ esteja definida em $z_0$ e que, por fim, o valor que a função assume em $z_0$ seja igual ao seu limite nesse ponto, caso qualquer uma dessas condições seja descumprida, dizemos que $f$ é descontínua em $z_0$.

Utilizando então a relação que definimos entre o limite de uma função complexa e os limites de suas componentes real e imaginária $u$ e $v$, podemos definir que:

> Se $f(z) = u(x,y) + iv(x,y)$, $z_0 = x_0 + iy_0$, a função $f$ é contínua em $z_0$ se e somente se as duas [[Funções de mais de uma variável|funções reais]] $u$ e $v$ forem contínuas em $(x_0, y_0)$

Assim, dadas duas funções $f$ e $g$ contínuas, vale que as seguintes funções também são contínuas:
1. $cf\,; c \in \mathbb C$
2. $f \pm g$
3. $f\cdot g$
4. $\frac f g\,; g \neq 0$

Assim, todas as funções polinomiais são contínuas em $\mathbb C$ bem como todas as funções racionais são contínuas em todo o seu domínio

