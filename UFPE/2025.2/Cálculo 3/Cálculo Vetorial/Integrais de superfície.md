Assim como definimos as [[Integrais de linha]] como integrais ao longo de uma [[Parametrização de curvas|curva]], podemos também definir integrais ao longo de uma [[Parametrização de superfícies|superfície]], seja com [[Função|funções]] escalares ou vetoriais, assim, temos:

> Seja $\mathcal S$ uma superfície e $\vec r(u,v) = x(u,v)\hat{i} + y(u,v)\hat{j} + z(u,v)\hat{k}$ uma parametrização para essa superfície, a integral da função escalar $f$ sobre a superfície $S$ é:
> $$\iint\limits_\mathcal S f(x,y,z)\,dS = \iint\limits_\mathcal D f(x,y,z)\left|\dfrac{\partial r}{\partial u} \times \dfrac{\partial r}{\partial v}\right|\,du\,dv$$
> Onde $\mathcal D$ é o domínio sobre o qual definimos os parâmetros $u$ e $v$.

Note que, se $f(x,y,z) = 1$, então a integral resulta na área da superfície parametrizada:

$$
\iint\limits_\mathcal S dS = \iint\limits_\mathcal D\left|\dfrac{\partial r}{\partial u} \times \dfrac{\partial r}{\partial v}\right|\,du\,dv = A
$$

No caso em que $f$ é substituída por uma função vetorial $F$, passamos então a ter o que chamamos de integral de fluxo:

> Seja $\mathcal S$ uma superfície e $\vec r(u,v) = x(u,v)\hat{i} + y(u,v)\hat{j} + z(u,v)\hat{k}$ uma parametrização para essa superfície, o fluxo do [[Campos vetoriais|campo vetorial]] $F$ através da superfície $S$ é:
> $$\iint\limits_\mathcal S F(x,y,z)\,dS = \iint\limits_\mathcal D F(x,y,z)\left(\dfrac{\partial r}{\partial u} \times \dfrac{\partial r}{\partial v}\right)\,du\,dv$$
> Onde $\mathcal D$ é o domínio sobre o qual definimos os parâmetros $u$ e $v$.

Um problema que pode surgir é quanto a utilização de $\dfrac{\partial r}{\partial u} \times \dfrac{\partial r}{\partial v}$ ou  $\dfrac{\partial r}{\partial v}\times \dfrac{\partial r}{\partial u}$, devido as propriedades do **produto vetorial**, o fluxo tem sinal inverso quando invertermos esse produto, assim, dependendo de nosso objetivo, precisamos escolher uma orientação para a nossa superfície, dessa maneira, só podemos trabalhar dessa maneira com superfícies que são **Orientáveis**, ou seja, superfícies nas quais seja possível definir um vetor normal $\vec n$ que varie continuamente sobre toda a superfície $\mathcal S$, além disso, toda superfície orientável possui duas orientações possíveis.