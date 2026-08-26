De forma não explícita, já aprendemos a resolver [[EDO's Lineares de Primeira Ordem]] homogêneas, equações da forma:

$$
\dot x + px = 0
$$

Já que estas são [[Equações Separáveis]] e portanto podem ser resolvidas com o método da [[Separação de variáveis]], isto, é, podemos reescrever equações desse tipo como:

$$
\dfrac {\dot x} x= -p
$$
$$
\ln |x| = -\int p\,dt + c_1
$$
$$
|x| = e^{c_1}e^{-\int p\,dt} 
$$
$$
x = Ce^{-\int p\,dt} 
$$

Resolvendo então, com uma facilidade que depende da dificuldade da integral de $p$, as EDO's lineares Homogêneas, por fim, uma notação que será útil mais pra frente é obtida encontrando alguma solução para $e^{-\int p\,dt}$ e chamando essa solução de $x_h(t)$ e denotando então:

$$
x = Cx_h(t)
$$

Esse método, no entanto, não ajuda muito com as EDO's lineares não homogêneas e por isso, utilizaremos o chamado **Método dos Fatores Integrantes**.

Dada uma EDO Linear de primeira ordem não homogênea:

$$y^\prime + p(x)y(x) = q(x)$$

A ideia é multiplicar ambos os lados da equação por um **fator integrante** $u(x)$ tal que o lado direito da equação seja $u(x)(y^\prime + p(x)y(x)) = (ux)^\prime$ e o lado esquerda seja então $q(x)u(x)$, ou seja:

$$u(y^\prime + py) = (uy)^\prime  =   qu$$

Já que assim, podemos resolver a equação apenas integrando de ambos os lados:

$$uy = \int qu\,dx $$

Então:

$$y(x) = \dfrac 1 {u(x)} \int q(x)u(x)\,dx$$

Por fim, sabemos que $(uy)^\prime = u^\prime y + uy^\prime = uy^\prime + upy$, então:

$$u^\prime = up \implies \dfrac {u^\prime} u = p \implies u(x) = e^{\int p\,dx}$$

Portanto, para qualquer EDO Linear desse tipo e nessa forma, a solução é:

$$y(x) = \dfrac 1 {u(x)} \int q(x)u(x)\,dx \text{, onde } u(x) = e^{\int p\,dx}$$

Portanto, podemos aplicar o método dos fatores integrantes seguindo os passos:

1. Coloque a EDO na forma linear padrão $y^\prime + py = q$
2. Encontre o fator integrante resolvendo $u = e^{\int p\,dt}$
3. Multiplique ambos os lados da EDO pelo fator integrante encontrado, nessa etapa vale também conferir a solução da integral derivando $(uy)^\prime$
4. Integre a equação e encontre sua solução geral, caso necessário, encontre através da solução geral uma solução específica conveniente