---
tags:
  - Definição
  - Fórmula
  - Procedimento
---
Uma das principais aplicações das [[Derivada|derivadas]] na engenharia é a Aproximação Linear, também chamada de linearização,  muito útil para transformar funções complicadas  em funções mais simples e que permitam ver com mais clareza a relação entre as variáveis. 

Sabemos que a [[O problema da reta tangente|reta tangente]] a um determinado ponto do gráfico de $f(x)$ pode representar também a sua taxa de variação infinitesimal, sabemos também, agora nomeando os objetos, que para uma reta tangente ao ponto $P = (a, f(a))$ na curva de $f(x)$ o ponto em questão é comum ao gráfico da função e à reta tangente, o que nos leva a concluir que quanto mais perto do ponto $P$ estamos considerando, mais próximos estão os valores da gráfico da reta tangente com ralação ao gráfico de $f(x)$. É nessa ideia que se baseia a aproximação linear. Temos portanto:
$$
f(x) \approx f(a) + f^\prime(a)(x-a), \ \ \text{para} \ \ x \approx a
$$
Uma notação que também é muito usada é:
$$
\Delta y = f^\prime(a) \Delta x, \ \ \text{para} \ \ \Delta x \approx 0
$$Algumas aproximações lineares básicas e úteis são:
(Considere $x \approx 0$)

|    $f(x)$    | Aproximação |
| :----------: | :---------: |
| $(1 + x)^r$  |  $1 + rx$   |
|  $\sin{x}$   |     $x$     |
|  $\cos{x}$   |     $1$     |
|    $e^x$     |   $1 + x$   |
| $\ln(1 + x)$ |     $x$     |

A parte mais útil disso é que podemos aplicar a ideia, mesmo sem muito cálculo para simplificar funções através da tabela acima, veja:
$$
m = \dfrac{m_0c}{\sqrt{c^2 - v^2}}
$$
A função parece bem complicada, podemos começar tirando a constante $m_0$ da fração:
$$m = m_0\dfrac{c}{\sqrt{c^2 - v^2}}$$
Podemos dividir o numerador e  o denominador por $c$, obtendo:
$$m = m_0\dfrac{1}{\sqrt{1 - \dfrac{v^2}{c^2}}} = m_0(1-\dfrac{v^2}{c^2})^{\dfrac{1}{2}}$$
Agora aplicamos a aproximação como vimos na tabela:
$$m = m_0(1-\dfrac{v^2}{2c^2})$$
