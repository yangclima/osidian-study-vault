---
tags:
  - Procedimento
---
A resolução de [[Derivada|derivadas]] através de sua definição, ou seja, usando limites é demorada e complexa, por isso, existem métodos e regras para facilitar a resolução de determinados grupos de derivadas como veremos a seguir.
## Derivada de uma constante
Como uma função constante é uma reta horizontal, a reta tangente à essa função também o será, sendo assim, tem inclinação 0. 
$$
\dfrac{d}{dx} c = 0
$$
## Derivada de uma potência de $x$
Essa solução deriva da aplicação do Teorema do [[Binômio de Newton]] na definição da derivada, obtendo o seguinte:
$$
\dfrac{d}{dx} x^n = nx^{n-1}
$$
## Derivada de uma função multiplicada por uma constante 
Devido às propriedades dos limites, temos que, se uma função estiver sendo multiplicada por uma constante podemos "tirar" essa constante do limite, obtendo:
$$
\dfrac{d}{dx} \  c \cdot  f(x) = c \cdot  \dfrac{d}{dx} \ f(x)
$$
## Derivada da soma
Mais uma vez por conta da propriedades dos limites temos:
$$
\dfrac{d}{dx} \ [ f(x) + g(x)] = \dfrac{d}{dx} \ f(x) \ + \ \dfrac{d}{dx} \ g(x) 
$$
## Derivada do produto
Sobre a derivada da soma de duas funções temos:
$$
\dfrac{d}{dx} \ f(x) \cdot g(x) = g(x) \dfrac{d}{dx} \ f(x) + f(x) \dfrac{d}{dx} \ g(x) 
$$
## Derivada do quociente
Sobre a derivada do quociente de duas funções temos:
$$
\dfrac{d}{dx} \ \dfrac{f(x)}{g(x)} =  \dfrac{g(x) \dfrac{d}{dx} \ f(x) - f(x) \dfrac{d}{dx} \ g(x)}{g(x)^2}
$$
## Derivada de função composta
Ao receber uma função como $y = (x+5)^{100}$ podemos considera-la uma função composta, de tar forma que poderíamos fazer: $u = x + 5$, e dessa forma: $y = u^5$, nesses caso teríamos o seguinte:
$$
\dfrac{dy}{dx} = \dfrac{dy}{du} \dfrac{du}{dx}
$$
Ou, da mesa maneira:
$$
[f(g(x))]^\prime = f^\prime(g(x)) \cdot g^\prime(x) 
$$
## Derivada de função implícita
Algumas funções podem ser apresentadas com vários termos mistos de $x$ e $y$ de tal forma que podemos definir $x$ através de processos algébricos, contudo, muitas vezes esse processo é muito complexo, nesse sentido podemos utilizar o método chamado "Derivação implícita", o segredo é deriva $y$ de forma a sempre considerar que este é uma função de $x$, pro exemplo:
$$
x^3 + y^3 = xy
$$
Fazemos então:
$$
3x^2 + 3y^2 \cdot y^\prime = y + y^\prime x
$$
Perceba que derivamos o termo de y como uma regra da cadeia, pois estamos derivando a função $y = f(x)$, da mesma forma que resolvemos o termo misto de $y$ com a regra do produto. Nosso objetivo agora é isolar o $y^\prime$, nosso propósito inicial.
$$
3y^2 \cdot y^\prime - y^\prime x = y - 3x^2
$$
$$
y^\prime =\dfrac{y- 3x^2}{3y^2-x}
$$