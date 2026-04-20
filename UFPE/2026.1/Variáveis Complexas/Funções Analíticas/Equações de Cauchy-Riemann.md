Agora que conhecemos a [[Diferenciabilidade e Analiticidade]] das [[Funções Complexas]] podemos estabelecer uma séria de fatos e teoremas que nos fornecerão formas mais simples de verificar tanto a diferenciabilidade quanto a analiticidade de uma função, sem recorrer a [[Limites e Continuidade de funções Complexas|limites]].

> Suponhamos que $f(x,y) = u(x,y) + iv(x,y)$ é diferenciável em um ponto $z = z +iy$. Então, em $z$, as [[Derivadas parciais]] de primeira ordem de $u$ e $v$ devem satisfazer as seguintes equações:
> $$\dfrac{\partial u}{\partial x}= \dfrac{\partial v}{\partial y} \ \ \ \text{e} \ \ \ \dfrac{\partial u}{\partial y}= - \dfrac{\partial v}{\partial x}$$
> Essas equações são chamadas de **Equações de Cauchy-Riemann**


Note que essas equações não conseguem nos provar que uma função é diferenciável em um ponto $z$ qualquer já que sua validade depende justamente da diferenciabilidade de $f$, no entanto, **se essas equações não forem satisfeitas isso nos prova automaticamente que a função não é diferenciável em $z$**, além disso, esse teorema implica que se $f$ for analítica em todo um domínio $D$, as funções $u$ e $v$ satisfazem Cauchy-Riemann em todos os ponto de $D$ de forma que vale o seguinte critério sobre a analiticidade de $f$:

> Se as equações de Cauchy-Riemann não forem satisfeitas em algum ponto de um domínio $D$, a função $f(z) = u(x,y) + iv(x,y)$ não pode ser analítica em $D$

Se adicionarmos, no entanto, exigências quanto a continuidade das funções $u$ e $v$ bem como de suas derivadas parciais podemos chegar em um novo teorema que nos garante a analiticidade da função:

> Sejam as funções $u(x,y)$ e $v(x,y)$, funções reais [[Limite e Continuidade de funções de mais de uma variável|contínuas]] e que possuem derivadas parciais de primeira ordem também contínuas em um domínio $D$. Se $u$ e $v$ satisfizerem as equações de Cauchy-Riemann em todos os pontos de $D$, então a função complexa $f(z) = u(x,y) + iv(x,y)$ é analítica em $D$

Ou, quanto a diferenciabilidade:

> Sejam as funções $u(x,y)$ e $v(x,y)$, funções reais [[Limite e Continuidade de funções de mais de uma variável|contínuas]] e que possuem derivadas parciais de primeira ordem também contínuas em alguma [[Conjuntos de pontos no plano complexo|vizinhança]] do ponto $z$, se $u$ e $v$ satisfizerem as equações de Cauchy-Riemann em $z$, então a função $f(z) = u(x,y) + iv(x,y)$ é diferenciável

Além disso, se de fato $f$ for diferenciável, sua derivada é dada por:

$$f^\prime(z) = \dfrac{\partial u}{dx} + i\dfrac{\partial v}{dx} = \dfrac{\partial v}{dy} - i\dfrac{\partial u}{dy}$$

Essas observações  trazem então algumas conclusões sobre funções que aparecem frequentemente em nossos cálculos, por exemplo:

> Se a função $f(z) = u(x,y) + iv(x,y)$ for analítica em um domínio $D$ então vale que
> 
> 1) Se $f$ for constante, isto é, $|f(z)| = c$ em $D$, $f(z)$ também é constante
> 2) Se $f^\prime(z) = 0$ em $D$, $f(z) = c$ em $D$, onde $c$ é uma [[Números Complexos|constante complexa]]
> 

Podemos também pensar nas equações de **Cauchy-Riemann** para a [[Forma polar de números Complexos|forma polar]], isto é, quando $f(z) = u(r,\theta) +iv(r,\theta)$. Nesse caso vale que:

$$\dfrac{\partial u}{\partial r} = \dfrac{1}{r}\dfrac{\partial v}{\partial \theta} \ \ \ \text{e} \ \ \ \dfrac{\partial v}{\partial r} = -\dfrac{1}{r}\dfrac{\partial u}{\partial \theta}$$

E sua [[Derivada]] é dada por:

$$f^\prime(z) = e^{-i\theta}\left(\dfrac{\partial u}{\partial r} + i\dfrac{\partial v}{\partial r} \right) = \dfrac{1}{r}e^{-i\theta}\left(\dfrac{\partial v}{\partial \theta} - i\dfrac{\partial u}{\partial \theta} \right)$$


