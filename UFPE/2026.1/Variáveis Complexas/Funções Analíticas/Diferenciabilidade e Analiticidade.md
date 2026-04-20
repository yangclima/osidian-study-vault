Dado um [[Números Complexos|número complexo]] $z_0 = x_0 + iy_0$ e o ponto arbitrário do [[O plano complexo|plano complexo]] $z = x+ iy$ uma mudança em $z_0$ é a diferença $\Delta z = z - z_0$, ou seja $\Delta z = (x-x_0) + i(y-y_0) = \Delta x + i\Delta y$. Se uma [[Funções Complexas|função complexa]] $f(z)$ for definida em $z$ e $z_0$, a correspondente mudança na função é dada pela variação de $\Delta w = f(z+\Delta z) - f(z_0)$.

Com isso definimos a **derivada** de uma função complexa $f$ qualquer em termos de um [[Limites e Continuidade de funções Complexas|limite]] do quociente de variações $\Delta w / \delta z$ à medida que $z \to z_0$, ou seja:

> Se $f$ a função complexa definida na vizinhança de $z_0$, a derivada de $f$ em $z_0$, denotada por $f^\prime(z_0)$ é definida por
>  $$f^\prime(z_0) = \lim\limits_{\Delta z\to 0} \dfrac{f(z_0+\Delta z) - f(z_0)}{\Delta z}$$
>  Desde que esse limite exista.

A grande diferença aqui é que, devido a definição do limite de funções complexas depender do fato de o limite existir e ser independente da direção de aproximação a exigência de derivabilidade é muito mais rígida aqui.

> DICA:  Se uma função complexa for montada a partir da especificação de suas partes real e imaginária $u$ e $v$, como $f(z) = x+4iy$, é grande a probabilidade de que não seja diferenciável.

Ao lidar com derivadas de números complexos, valem todas as propriedades e regras convencionais das [[Derivada|derivadas]] de [[Funções]] reais, inclusive a regra da potência.

Embora a exigência de diferenciabilidade seja severa, existe uma classe de funções tão importantes que seus membros devem satisfazer exigência ainda mais severas, estas são as denominadas **funções analíticas**.

> Uma função complexa $w= f(z)$ é **analítica** em um ponto $z_0$ se $f$ for diferenciável nesse ponto em em todo ponto de alguma vizinhança de $z_0$ ou analítica em todo o [[Conjuntos de pontos no plano complexo|domínio]] $D$ caso seja analítica em todo ponto em $D$.

Além disso, se $f$ for analítica em todo [[O plano complexo]], ela é dita uma **função inteira**, esse é o caso de todas as funções polinomiais complexas (Coeficientes inteiros) e uma função racional complexa é analítica em todo domínio $D$ que não contenha nenhum ponto onde seu denominador se anula.

Chamamos os pontos onde uma função $w = f(z)$ não é analítica de **pontos singulares** de $f$. 

Vale notar que dadas duas funções quaisquer analíticas em um domínio $D$, $f$ e $g$, suas soma, diferença e produto são também analíticas, além disso, o seu quociente também o é, a menos que $D$ contenha um ponto onde seu denominador se anula.

Assim como para uma [[Função]] real, se $f$ for diferenciável em um ponto $z_0$ em um domínio $D$, isso implica que $f$ é [[Limites e Continuidade de funções Complexas|contínua]] em $z_0$.

Outra observação muito útil e importante é que a Regra de L'Hôpital também funciona para funções complexas desde que estas sejam analíticas.