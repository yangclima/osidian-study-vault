O problema de Dirichlet consiste basicamente em procurar, para um determinado [[Conjuntos de pontos no plano complexo|Domínio]] $D$ e uma [[Função]] $g(x,y)$, uma função $\phi(x,y)$ [[Funções Harmônicas|harmônica]]  em $D$ e que seja igual a $g(x,y)$ em sua fronteira.

 Esse problema surge em variáveis complexas com uma aplicação das [[Transformações complexas]] e [[Funções Complexas]], basicamente sustentadas pelo seguinte teorema:

> Seja $f(z) = u(x,y) + iv(x,y)$ uma transformação [[Diferenciabilidade e Analiticidade|analítica]] de $D$ em $D^\prime$ , se a função $\phi(u,v)$ satisfizer a equação de Laplace em $D^\prime$, então $\phi(u(x,y),v(x,y))$ é harmônica em $D$

Assim, para resolver com maior simplicidade esse problema podemos seguir os passos:

1. Determinamos uma função que mapeia o domínio original $D$ 
2. Mapeamos as condições de contorno para o novo domínio
3. Resolvemos o problema de Dirichlet no novo domínio
4. Retornamos para o domínio anterior

