O termo $a_{-1}$ da expansão em [[Séries de Laurent]] de uma [[Funções Complexas|função complexa]] tem uma enorme importância e por isso recebe o nome especial de **Resíduo**, denotado da seguinte forma:

$$a_{-1} = \text{Res}(f(z),z_0) $$

Para obter esse resíduo, normalmente não precisaremos recorrer a expansão em séries de Laurent ou mesmo o cálculo de seus coeficientes, isso por que:

1. Se a [[Funções Complexas|função]] $f$ tiver um [[Zeros e Polos|polo simples]] em $z=z_0$ então $$a_{-1} = \text{Res}(f(z),z_0) = \lim_{z\to z_0}(z-z_0)f(z)$$Quando, no entanto, a função $f$ não for uma função racional mas for possível escrevê-la em termos da divisão de duas funções $h(z)$ e $g(z)$ tal que $f(z) = g(z)/h(z)$ e tanto $h$ quanto $g$ são analíticas em $z_0$ então, se $g(z_0)\neq 0$ e $f$ tem um polo simples em $z_0$ vale que $$a_{-1} = \text{Res}(f(z),z_0) = \dfrac{g(z_0)}{h^\prime(z_0)}$$
2. Se $f$ tiver um polo de ordem $n$ em $z=z_0$ então $$a_{-1} = \text{Res}(f(z),z_0) = \dfrac{1}{(n-1)!}\lim_{z\to z_0}\dfrac{d^{(n-1)}}{dz^{(n-1)}}(z-z_0)^nf(z)$$

A grande utilidade dos resíduos se dá pelo seguinte teorema:

> Seja $D$ um [[Conjuntos de pontos no plano complexo|Domínio]] simplesmente conexo e seja $C$ um contorno fechado simples totalmente posicionado em $D$ se $f$ for [[Diferenciabilidade e Analiticidade|analítica]] em $C$ e  no interior de $C$, exceto em um número finito de singularidades isoladas $z_1,z_2,\cdots,z_n$ no interior de $C$, vale que:
> $$\oint_C f(z)dz = 2\pi i \sum_{k=1}^n \text{Res} (f(z), z_k)$$ 

Este teorema é chamado de **Teorema dos Resíduos de Cauchy**. Além disso, mesmo que a função $f(z)$ tenha uma singularidade essencial, isto é, um polo de ordem infinita, o teorema ainda funciona, mesmo que o resíduo não seja tão fácil de calcular.