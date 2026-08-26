Caso uma [[Funções Complexas|função complexa]] $f$ deixe de ser analítica em um ponto $z_0$, denominamos esse ponto como **Singularidade** ou **Ponto Singular** de $f$, estendendo a definição, dizemos que uma singularidade $z_0$ de uma função é uma **Singularidade isolada** se existir alguma [[Conjuntos de pontos no plano complexo|vizinhança deletada ou disco aberto perfurado]] $0 < |z-z_0| < R$ em que $f$ é analítica, por outro lado, dizemos que esse ponto singular é **não isolado** se qualquer uma das suas vizinhanças contiver pelo menos uma singularidade de $f$ que não seja $z_0$.

É óbvio que se $z_0$ é uma singularidade de $f$ não podemos representar essa função como uma [[Séries de Taylor Complexas|Série de Taylor]] centrada em $z_0$, é possível, no entanto, representar essa função por uma série que envolve potências inteiras negativas e não negativas de $z-z_0$, uma [[Sequências e Séries complexas|série]] cuja forma é representada pela soma de duas séries:

$$f(z) = \sum_{k=1}^{\infty}a_{-k}(z-z_0)^{-k} + \sum_{k=0}^\infty a_k(z-z_0)^k$$


O primeiro somatório, com potências negativas, é chamada de **Parte principal** da [[Séries|série]], enquanto o segundo, com potências positivas é chamada de **parte analítica** da série (Ou parte Tayloriana), e essa série, pode ser escrita de maneira mais compacta como:

$$\sum_{k=-\infty}^\infty a_k(z-z_0)^k$$

Essa representação em série de uma função é denominada **Série de Laurent** ou **Expansão de Laurent** de $f$ em torno de $z_0$ na região anelar definida por $r < |z-z_0| < R$.

Quanto a isso, temos o teorema de Laurent:

> Seja $f$ uma função [[Diferenciabilidade e Analiticidade|analítica]] num domínio $D$ anelar definido por $r < |z-z_0| < R$, então $f$ tem a representação em série:
> $$f(z) = \sum_{-\infty}^\infty a_k(z-z_0)^k$$
> Válida para todos os pontos da região  $r < |z-z_0| < R$, onde os coeficientes $a_k$ são dados por:
> $$a_k = \dfrac{1}{2\pi i}\oint_C\dfrac{f(s)}{(s-z_0)^{k+1}}ds\,; \ k=0,\pm 1,\pm 2,\pm 3,\cdots$$
> Onde $C$ é uma curva qualquer, fechada, simples, totalmente posicionada em $D$ e que tenha $z_0$ em seu interior.

Se todos os coeficientes $a_{-k}$ forem $0$, podemos ver que os coeficientes representam as derivadas da função através das [[Fórmulas Integrais de Cauchy]] sendo assim, nesse caso, a série se resume à série de Taylor da função, sendo então, a série de Laurent, uma generalização das séries de Taylor.

Os coeficientes definidos no teorema, no entanto, são complicados de calcular na prática, por isso, é comum que obtenhamos as séries de Laurent de uma função através da manipulação das [[Séries de Taylor e Maclaurin]] de outra ou manipulando a [[Séries Notáveis#Série geométrica|série geométrica]].

