Uma das grandes aplicações do [[Resíduos|Teorema dos Resíduos]] é para o cálculo de [[Integral definida|Integrais]] reais, onde, através dele, resolvemos em especial dois tipos de integrais: 

1. $\int_0^{2\pi}F(\cos\theta,\sin\theta)d\theta$
2. $\int_{-\infty}^\infty f(x)dx$

No primeiro caso, fazemos basicamente uma mudança de variáveis reescrevendo a integral conforme a seguinte relação:

$$\int_0^{2\pi}F(\cos\theta,\sin\theta)d\theta = \int_{\mathcal{C(0,1)}}F\left(\dfrac{1}{2}(z+z^{-1}), \dfrac{1}{2i}(z-z^{-1})\right)dz$$

Onde $z=e^{i\theta}$, $\theta \in [0,2\pi]$ e $dz = i\theta e^{i\theta}d\theta$

E então pelo teorema:

$$\int_{\mathcal{C(0,1)}}F\left(\dfrac{1}{2}(z+z^{-1}), \dfrac{1}{2i}(z-z^{-1})\right)\dfrac{dz}{iz} = 2\pi i\sum_{k=1}^n \text{Res}(f(z), z_k)$$

Dessa forma, resolvemos qualquer função de senos e cossenos cujos limites de integração são 0 e $2\pi$.

Quanto a aplicação em integrais impróprias, quando temos uma integral do tipo:

$$\int_{-\infty}^{\infty}f(x)dx$$

Associada a ela temos um limite especial chamado de **Valor Principal de Cauchy** da integral:

$$
\lim\limits_{R\to\infty}\int_{-R}^R f(x)dx = V.P\int_{-\infty}^{\infty}f(x)dx
$$

Se essa integral converge, ela converge para essa valor principal, se ela diverge, ainda assim o limite pode existir.

No caso dessas integrais, o procedimento básico é:

Seja $f(x) = p(x)/q(x)$ contínua em $(-\infty,\infty)$ substituímos $x$ pela variável complexa $z$ e integramos a [[Funções Complexas|função complexa]] em um contorno fechado $C$ que consiste no intervalo $[-R,R]$ no eixo real e uma semicircunferência $C_R$ de raio suficientemente grande de modo a  envolver todos os [[Zeros e Polos|polos]] da função que ocorrem no semiplano $Im(z)> 0$.

Assim, se pudermos mostrar que $\int_{C_R}f(z)dz \to 0$ quando $R \to \infty$ teremos:

$$
V.P\int_{-\infty}^{\infty}f(x)dx = 2\pi i\sum_{k=1}^n\text{Res}(f(z), z_k)
$$

Quanto a provar que a integral sobre $C_R$ zera com $R$ indo pro infinito, podemos assumir isso imediatamente desde que o grau do numerador de seja pelo menos  duas vezes menor que o do denominador. 

Outra afirmação interessante é sobre funções pares, para elas, desde que exista o valor principal de Cauchy, a integral imprópria será convergente.

Como caso final de aplicação, temos integrais da forma

$$
\int_{-\infty}^\infty f(x)\cos{(\alpha x)} \ \ \ \ \ \text{e} \ \ \ \ \ \int_{-\infty}^\infty f(x)\sin{(\alpha x)}
$$

Denominadas Integrais de Fourier que aparecem como a parte real e imaginária da integral

$$\int_{-\infty}^\infty f(x)e^{i\alpha x} = \int_{-\infty}^\infty f(x)\cos{(\alpha x)} + i\int_{-\infty}^\infty f(x)\sin{(\alpha x)}$$

Usando a [[Fórmula de Euler]]. Sempre que o lado direito dessa equação converge, podemos calcular, ambas as integrais de Fourier simultaneamente usando a integral complexa, como visto anteriormente.

Sempre que $f(z) = p(z)/q(z)$ é tal que o grau de $p$ é pelo menos duas vezes menor que o de $q$, se $C_R$ for um contorno semicircular $z = Re^{i\theta}$, $\theta \in [0,\pi]$ e 
$\alpha > 0$ então, para $R \to 0$:

$$
\int_{C_R} f(z)e^{i\alpha z}dz \to 0
$$

Esse procedimento básico visto até aqui precisa ser modificado usando um contorno denteado no caso de existirem polos da função sob o eixo real, usando que:

$$\lim\limits_{r\to 0}\int_{C_r}f(z)dz = \pi i \text{Res}(f(z), c) $$

