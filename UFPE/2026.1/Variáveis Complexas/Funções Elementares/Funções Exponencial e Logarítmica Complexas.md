# Função exponencial Complexa
A função $e^z$ definida como:

$$e^z = e^x\cos{y} + ie^x\sin y$$

É a chamada **Função Exponencial Complexa**. Essa função é muito interessante e reproduz algumas importantes características da função exponencial complexa, coincidindo com a própria quando $z$ é um número real (Um [[Números Complexos|número complexo]] sem parte imaginária) e cuja derivada é a própria função, sendo a única função possível que reproduz essas duas características, além disso, é [[Diferenciabilidade e Analiticidade|analítica]] em todo o [[O plano complexo|plano complexo]], isto é, uma função inteira.

O módulo o argumento e o conjugado dessa função são facilmente calculados usando as [[Aritmética de números complexos]] e são dados por:

$$|e^z| = e^z$$
$$\arg(e^z) = y + 2n\pi\,; \ n = 0, \pm1,\pm2,\cdots$$
$$\overline{e^z} = e^{\overline{z}}$$

E valem pra ela as mesmas propriedades algébricas da exponencial real, já que sendo dois números complexos quaisquer $z_1$ e $z_2$:

$$e^0 = 1$$
$$e^{z_1}e^{z_2} = e^{z_1 + z_2}$$
$$\dfrac{e^{z_1}}{e^{z_2}} = e^{z_1 - z_2}$$
$$(e^z)^n = e^{nz}$$

A diferença mais notável, no entanto, entre a exponencial real e a complexa é que a complexa é Periódica. Dizemos que uma função complexa é periódica com período $T$ se ela satisfaz $f(z + T) = f(z)$ para todos os [[Números Complexos]], nesse caso, temos que $e^z$ é periódica com período puramente imaginário $2\pi i$ já que:

$$e^{z + 2\pi i} = e^z; $$

No entanto, com isso percebemos que a função exponencial $e^z$ não é uma função biunívoca, uma vez que $e^{z+2n\pi i} = e^z$, para todo $n \in \mathbb Z$. Assim, diferentes valores de $z$ podem produzir o mesmo valor da função. Além disso, todos os valores possíveis de $e^z$ se repetem em faixas horizontais de comprimento infinito e largura $\pi$ no plano complexo, sendo essa largura medida ao longo do eixo imaginário. Isto é, cada faixa desse tipo contém, por si só, todos os valores possíveis da função, definimos então a faixa:

$$-\infty < x < \infty\,; \ -\pi \leq y \leq \pi$$

Como a **região fundamental** da função exponencial complexa.

Analisemos agora a chamada [[Transformações complexas|transformação]] exponencial em alguns casos, por exemplo, vejamos o que ocorre com a a [[Conjuntos de pontos no plano complexo|região]] fundamental quando mapeada pela transformação complexa $w = e^z$: Podemos [[Parametrização de superfícies|parametrizar]] essa faixa como 

$$z(t) = a + it\,; \ a \in (-\infty,\infty)\,; \ t \in [-\pi, \pi]$$

Assim temos:

$$w(z) = e^{a + it} = e^ae^{it} = e^a(\cos{t} + i\sin{t})$$

Desse modo, como $a$ corresponde a qualquer número real, temos aqui a região formada por todos os círculos de raio não nulo, já que $e^a > 0$, isto é, o plano complexo com exceção da origem, o que significa que:

> A região fundamental da função exponencial é mapeada por $w = e^z$ no conjunto de pontos $|z| > 0$, ou seja, conjunto de todos os números complexos não nulos

Pegando o embalo, se tivermos um segmento de reta vertical:

$$z(t) = a + it\, ; \ t\in (-\pi,\pi)$$

É mapeado na circunferência de raio $a$:

$$e^{a + it} = e^ae^{it} \ \ \ \text{ou} \ \ \ |z| = a$$

E de forma semelhante, o segmento de reta horizontal:

$$z(t) = t + ib\,; \ t \in (-\infty,\infty)$$

É mapeado para o raio de ângulo $b$:

$$e^{t + ib} = e^te^{ib} \ \ \ \text{ou} \ \ \ \arg{z} = b$$

# Função Logarítmica Complexa
Ao lidar com números reais, frequentemente nos referimos a função logaritmo natural ou $\ln$ como a inversa da função exponencial real, aqui, nos números complexos isso é um pouco mais complicado, a função $e^z$ não é biunívoca em todo o seu domínio, portanto não podemos definir uma função inversa para a função exponencial complexa que funcione em todo o seu domínio, ainda assim, queremos resolver equações do tipo $e^w = z$, onde $w = u + iv$ é a incógnita e $z$ é um número complexo qualquer. Note então que usando a [[Forma polar de números Complexos]]:

$$e^w = e^{u+ iv} = e^ue^{iv} = |z|e^{i\arg(z)} \implies 
\begin{cases}
e^u = |z| \\
v = \arg(z) 
\end{cases} \implies
\begin{cases}
u= \log_e{|z|} \\
v = \arg(z) 
\end{cases}$$

Porém, como há infinitos valores para o argumento de um número complexo qualquer $z$, temos infinitas soluções para a equação então definimos a função multivalente:

$$\ln{z} = \log_e{|z|} + i\arg{(z)}$$

Chamada de **Logaritmo complexo**. Que de modo semelhante, aplicando a forma polar do número $z$ se torna:

$$\ln{(z)} = \ln{(re^{i\theta})} = \log_e{r} + i(\theta + 2n\pi)\,; \ n \in \mathbb Z$$

Essa função inclusive possui propriedades algébricas análogas às da da exponencial real, já que sendo $z_1$ e $z_2$ números complexos não nulos, vale que:

$$\ln{(z_1z_2)} = \ln{(z_1)}+ \ln{(z_2)}$$
$$\ln{\left(\dfrac{z_1}{z_2}\right)} = \ln{(z_1)}- \ln{(z_2)}$$
$$\ln{(z_1^n)}= n\ln{(z_1)}$$

Já sabemos que essa função é multivalente, podemos porém, tomar, ao invés do argumento de $z$, seu argumento principal, eliminando a ambiguidade dessa função, e definindo o **Valor principal do logaritmo complexo** como sendo:

$$\text{Ln}{(z)}  = \log_e{|z|} + i\text{Arg}{(z)}$$

No entanto isso traz algumas falhas, as propriedades algébricas do logaritmo real começam a falhar e as identidades que vimos não funcionam em geral.

Apesar da função $e^z$ não ser biunívoca, se a restringirmos à região fundamental ela passa a ser e então admite inversa que no caso é justamente o valor principal do logaritmo complexo, isto é, $\text{Ln}{(z)}$ e dessa maneira, para $z \neq 0$ e na região fundamental:

$$f(z) = e^z \implies f^{-1}(z) = \text{Ln}{(z)}$$

E assim a seguinte afirmação é valida para qualquer número complexo não nulo:

$$e^{\text{Ln}{(z)}} = z$$

E a seguinte é válida para qualquer número $z$ pertencente a região fundamental $R: \ x \in (-\infty,\infty)\; \ y\in[-\pi,\pi]$:

$$\text{Ln}{(e^z)} = z$$

Assim, quanto a [[Diferenciabilidade e Analiticidade|analiticidade]], a função do valor do logaritmo principal é analítica em todo o seu domínio, isto é, no ramo principal do logaritmo complexo e sua derivada é:

$$(\text{Ln}{(z)})^\prime = \dfrac{1}{z}$$

Quanto a transformação complexa definida por $w = \text{Ln}{(z)}$ podemos analisá-la em termos da exponencial complexa, já que são inversas, assim

> A transformação $w = \text{Ln}{(z)}$ mapeia os pontos da região $|z| > 0$ na região fundamental $-\infty < x < \infty\,; \ -\pi \leq y \leq \pi$.

> A transformação $w = \text{Ln}{(z)}$ mapeia os pontos da circunferência $|z| = r$ no segmento de reta vertical $u = \log_e{(r)}\,; \ -\pi < v < \pi$

> A transformação $w = \text{Ln}{(z)}$ mapeia os pontos do raio $\arg(z) = \theta$ no segmento de reta horizontal $v = \theta\,; -\infty < u < \infty$

