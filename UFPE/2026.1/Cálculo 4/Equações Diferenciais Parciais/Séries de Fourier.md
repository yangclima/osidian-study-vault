De forma análoga as [[Séries de Taylor e Maclaurin]], a série:

$$\dfrac{a_0}{2} + \sum_{m=1}^\infty a_m\cos{\left(\dfrac{m\pi x}{L}\right)} + b_m\sin{\left(\dfrac{m\pi x}{L}\right)} $$

Chamada de Série de Fourier, define, para os pontos nos quais converge, uma função $f(x)$ de modo que, se:

$$f(x) = \dfrac{a_0}{2} + \sum_{m=1}^\infty a_m\cos{\left(\dfrac{m\pi x}{L}\right)} + b_m\sin{\left(\dfrac{m\pi x}{L}\right)} $$

Dizemos que o membro direito é a **Série de Fourier de $f(x)$** e, devidas as amplas aplicações dessa série no cálculo de [[Equações Diferenciais]] Parciais, queremos formas de calcular os coeficientes $a_m$ e $b_m$ para definir completamente a série de Fourier de uma função $f(x)$.

Uma fórmula para esses coeficientes pode ser encontrada através da aplicação das chamadas **relações de ortogonalidade** e de propriedade de funções periódicas, de forma que:

$$a_m = \int_{-L}^Lf(x)\cos{\left(\dfrac{m\pi x}{L}\right)}dx; \ m\in \mathbb{N}$$
$$b_m = \int_{-L}^Lf(x)\sin{\left(\dfrac{m\pi x}{L}\right)}dx; \ m\in \mathbb{N}$$

Essas são as chamadas **Fórmulas de Euler-Fourier**.

Além disso, por uma elegante prova pode se chegar ao chamado **Teorema de convergência da série de Fourier**:

> Seja $f$ uma função e sua primeira [[Derivada]] $f^\prime$, seccionalmente contínuas num intervalo $-L < x < L$, de forma que, além disso, $f$ está definida fora desse intervalo sendo periódica com período $T = 2L$, então $f$ tem uma série de Fourier dada por:
> $$f(x) = \dfrac{a_0}{2} + \sum_{m=1}^\infty a_m\cos{\left(\dfrac{m\pi x}{L}\right)} + b_m\sin{\left(\dfrac{m\pi x}{L}\right)} $$
> Cujos coeficientes podem ser calculados pelas fórmulas de Euler-Fourier e que converge para $f(x)$ e, todos os pontos em que $f$ é contínua e para a média de seus limites laterais ($\dfrac{1}{2}(f(x^+)+f(x^-))$) em seus pontos de descontinuidade.


É necessário, no entanto, se atentar ao fato de que, apesar de serem suficientes, as condições dadas no teorema acima não são necessárias para a convergência da série de Fourier.