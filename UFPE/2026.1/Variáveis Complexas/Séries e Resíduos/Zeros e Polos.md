# Polos
Dada a expansão em [[Séries de Laurent]] de uma [[Funções Complexas|função]] $f$, podemos classificar um ponto singular $z_0$ dessa função com base no número de termos da parte principal dessa expansão:

1. **Singularidade Removível**: Se todos os termos da parte principal forem nulos.
2. **Polo**: Se a parte principal da expansão tiver um número finito de termos não nulos. (Se o $m$-ésimo termo da parte principal da série de Laurent de $f$ for não nulo, dizemos que a singularidade trata-se de um polo de ordem $m$, se $m=1$ dizemos que trata-se de um polo simples)
3. **Singularidade Essencial**: Se a parte principal da expansão tiver um número infinito de termos.

Se a função $f$ possuir uma singularidade no ponto $z=z_0$ sempre podemos definir adequadamente o valor de $f(z_0)$ de modo que essa função se torne analítica em $z_0$.
# Zeros
Dizemos que um ponto $z=z_0$ é um zero de uma função complexa $f(z)$ se $f(z_0) = 0$, além disso, dizemos que uma dada função [[Diferenciabilidade e Analiticidade|analítica]] tem um **zero de ordem $n$**, ou **zero de multiplicidade $n$** em $z=z_0$ se $z_0$ é um zero de suas $n-1$ primeiras derivadas, se um zero é de ordem $1$, também o chamamos de zero simples.

Definimos então o seguinte teorema:

> Se uma função $f$ é analítica em algum disco $|z-z_0|< R$, ela tem um zero de ordem $n$ em $z=z_0$ se e somente se ela puder ser escrita como
> $$f(z) = (z-z_0)^n\phi(z)$$
> Onde $\phi(z)$ é analítica em $z_0$.

Para então relacionar os polos e zeros de uma função chegamos na seguinte relação:

> Uma função $f$ é analítica em um disco perfurado $0<|z-z_0|<R$ tem um polo de ordem $n$ em $z=z_0$ se se somente se puder ser escrita como
> $$f(z) = \dfrac{\phi(z)}{(z-z_0)^n}$$
> Onde $\phi(z)$ é analítica em $z=z_0$ e $\phi(z_0)\neq0$

Além disso, podemos dizer que um ponto $z = z_0$ zero de uma determinada função $f$ é isolado caso exista alguma vizinhança desse ponto em que $f(z) \neq 0$ para todos os pontos, exceto para $z_0$. Nesse sentido, podemos afirmar que se $z_0$ é o zero de uma função analítica $f(z)$ então  uma função $g(z) = 1/f(z)$ terá uma singularidade isolada nesse mesmo $z_0$.

Dessa maneira, podemos deduzir o seguinte resultado:

> Se $g$ e $h$ forem funções analíticas em $z=z_0$ e $h$ tiver um zero de ordem $n$ em $z=z_0$ onde $g(z_0) \neq 0$, então a função $f(z) = g(z)/h(z)$ tem um polo de ordem $n$ em $z=z_0$.
