Seja $f$ uma [[Função|função]] de um conjunto $A$ no conjunto  $B$, se $f$ associar o elemento $a\in A$ ao elemento $b\in B$ dizemos que "$b$ é a **imagem** de $a$ sob $f$" ou que "$b$ é o valor de $f$ em a" e denotamos por $b = f(a)$, além disso, dizemos que o conjunto $A$ é o **domínio** de $f$ e que $B$ é a **imagem** de $f$, denotados por $Dom(f)$ e $Im(f)$ respectivamente, no entanto, ao dizer que $f$ é uma função de $A$ em $B$ não é necessário que $B$ seja a imagem de $f$ mas apenas que a imagem de $f$ esteja contida em $B$ , por exemplo:

$$\begin{cases}f:\mathbb R \to \mathbb R \\ f(x) = x^2\end{cases}$$

Apesar de $f$ ser uma função de $\mathbb R$ em $\mathbb R$, sua imagem são todos os números maiores ou iguais a $0$, e não $\mathbb R$ inteiro.

Nos casos com os quais estamos acostumados no cálculo e na matemática básica, consideramos sempre funções de uma ou [[Funções de mais de uma variável|mais variáveis]] reais, porém, definiremos agora as **Funções complexas**.

Um função complexa é uma função $f$ cujos conjuntos domínio e imagem são subconjuntos do conjunto dos [[Números Complexos]] $\mathbb C$, ou seja, uma generalização do nosso conceito anterior de função, por exemplo:

$$\begin{cases}f:\mathbb C \to \mathbb C \\ f(z) = z\bar z\end{cases}$$

Muitas vezes é útil expressar as entradas e saídas de uma função complexa em termos de suas partes real e imaginária, por exemplo

$$\begin{cases}f:\mathbb C \to \mathbb C \\ f(z) = z\bar z\end{cases} \ \ \equiv \ \ \begin{cases}f:\mathbb C \to \mathbb C \\ f(x + iy) = x^2 + y^2\end{cases}$$

Ou de forma similar:

$$w = f(z) = f(x+iy) = u + iv = z\bar z = x^2 + y^2 \implies \begin{cases}u = x^2 + y^2 \\ v = 0\end{cases}$$

De tal maneira que qualquer função complexa $f(z) = f(x+iy)$ pode ser expressa em termos de duas funções reais $u(x,y)$ e $v(x,y)$ denominadas, respectivamente, **parte real** e **parte imaginária** da função $f$, ou seja:

$$f(z) = f(x+iy) = u(x,y) + iv(x,y)$$

E então

$$w = f(z) = x^2 + y^2$$

É uma função complexa definida em termos das coordenadas cartesianas de $z$.

De tal maneira que qualquer função complexa definidas em termos de $u$ e $v$ podem ser expressas, se desejado, em termos de operações com $z$ e $\bar z$.

Ao lidar com a [[Forma polar de números Complexos]], utilizamos a **função exponencial complexa**, um exemplo de função definida pela especificação de suas partes real e imaginária de tal modo que:

$$w = u +iv = f(z) = f(x+iy) = e^z = e^x\cos y + ie^x\sin y \implies \begin{cases}u = e^x\cos y \\ v = e^x\sin y\end{cases}$$

Algo notável é que essa função nos permite expressar um número qualquer não nulo $z = r(\cos\theta + i\sin\theta)$ de forma particularmente conveniente como:

$$z = re^{i\theta}$$

No casos onde $z$ for um número real, a função exponencial complexa irá coincidir com a função exponencial real $f(x) = e^x$, e ambas tem várias semelhanças, apesar de que há entre elas algumas diferenças surpreendentes, dentre as quais a principal é que **A exponencial complexa é periódica**.

Além de expressarmos as as funções complexas como funções das partes real e imaginária da variável $z$, é igualmente válido aplicar os conceitos de coordenadas polares e, escrevendo $z = r(cos\theta + i\sin\theta)$ descrever uma função $w = f(z)$ qualquer em termos de duas funções reais de $r$ e $\theta$ $u(r,\theta)$ e $v(r,\theta)$, que representam as partes real e imaginária da imagem de $z$ sob $f$, por exemplo:

$$w = u +iv = f(z) = f(r(cos\theta + i\sin\theta) = z^2 = r^2(\cos^2\theta + 2i\cos\theta\sin\theta - \sin^2\theta)$$
$$w = r^2(\cos(2\theta) - i\sin(2\theta)) \implies \begin{cases}u = \cos(2\theta) \\ v = \sin(2\theta)\end{cases}$$

De modo que 

$$w = f(z) = \cos(2\theta) + i\sin(2\theta)$$

É uma função complexa definida em termos das coordenadas polares de $z$.