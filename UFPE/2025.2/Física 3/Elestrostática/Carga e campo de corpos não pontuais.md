Utilizando o [[Integral definida|cálculo diferencial e integral]] é possível analisar a [[Carga]] e o [[Campo Elétrico]] gerado por corpo não pontuais, o processo é intuitivo, a ideia é dividir o corpo $V$ em vários pedaços de volume $\Delta V$, onde o i-ésimo pedaço tem carga $\Delta q_i$

![[fg3_005.png| center]]

No limite do volume de cada pedaço tendendo a 0, esses pedaços se tornam infinitesimais e tem carga $dq$, ou seja:
$$
\lim_{\Delta V \rightarrow 0} \Delta q = dq
$$
E cada um desses pedaços infinitesimais gera um campo elétrico $d\vec{E}$ sobre o ponto $P$:
$$
d\vec{E}(P) = \dfrac{dq}{4\pi\varepsilon_0 \,r^2} \cdot \hat{r}
$$
Somando esses pedaços através de uma integração, obtemos então:
$$
\vec{E}(P) = \iiint\limits_{V} \dfrac{dq}{4\pi\varepsilon_0 \,r^2_{q,P}} \cdot \hat{r}_{q,P}
$$
Porém, até esse ponto a integral parece abstrata, o próximo passo é então analisar as condições do problema e reescrever $dq$, $r$ e $\hat{r}$ num sistema de coordenadas conveniente para a resolução e então encontrar os limites de integração que correspondam a iteração completa sobre o volume do corpo.

Por exemplo, para um anel delgado de raio $R$ no plano $xy$ e um ponto $P$ no seu eixo de simetria a uma altura $z$

![[fg3_006.png|center]]

$dq$ pode ser escrito como o produto de $\lambda$ (Coeficiente linear de distribuição de carga - carga por comprimento $Q/2\pi R$) vezes $Rd\theta$ (Comprimento do elemento infinitesimal de arco) e a razão $\hat{r}_{q,P}/{r^2_{q,P}}$ pode ser escrita  como $\vec{r}_{q,P}/r^3_{q,P}$ onde:
$$
\dfrac{\vec{r}_{q,P}}{r^3_{q_P}} = \dfrac{\vec{r}_{P} - \vec{r}_q}{r^3_{q_P}} = \dfrac{-R\hat{r} + z\hat{k}}{(R^2 + z^2)^{3/2}} = \dfrac{-R\cos{\theta}\hat{i} - R\sin{\theta}\hat{j} + z\hat{k}}{(R^2 + z^2)^{3/2}}
$$
E integrando de $0$ a $2\pi$ a expressão podemos obter  o campo elétrico do anel delgado. Em outras situações podem aparecer também coeficientes de distribuição de carga volumétricos ($\rho$) e de área ($\sigma$) e decompor vetorialmente o vetor posição é uma ferramenta poderosa para a resolução desse tipo de problema. No problema exemplificado, teríamos então a seguinte integral
$$
\int_0^{2\pi} k_e \cdot \dfrac{Q d\theta}{2\pi} \cdot \dfrac{-R\cos{\theta}\hat{i} - R\sin{\theta}\hat{j} + z\hat{k}}{(R^2 + z^2)^{3/2}}
$$
