Seguindo nas ideias da aproximação da ótica geométrica, começaremos a aplicar a ideia da propagação retilínea da [[Maxwell e a previsão das Ondas Eletromagnéticas|luz]] e a compreensão atual da [[Reflexão e refração|reflexão]] para entender as principais propriedades da formação de imagens em espelhos planos e esféricos olhando mais uma vez para a luz como fenômeno macroscópico.

# Formação de imagens em Espelhos planos
Consideremos primeiro o caso mais simples de formação de imagens, a **formação de imagens em espelhos planos**. 

Inicialmente, é importante distinguir entre a **reflexão especular** dos raios que incidem em uma superfície perfeitamente plana e a **reflexão difusa** de uma superfície rugosa. No primeiro caso, todos os raios de um feixe de luz paralelo que incidem na superfície obedecem em conjunto à **Lei da reflexão** e são refletidos ainda paralelos como um feixe de luz, no outro caso, cada raio obedece localmente essa lei e a superfície rugosa faz com que os raios sejam refletidos em diversas direções diferentes e, portanto, num espalhamento da luz, no mundo ideal consideramos uma reflexão especular, apesar disso, toda superfície real produz algum espalhamento da luz.

Veja a seguinte imagem que representa a formação de imagens num espelho plano.

![[fg4_002.png|700]]

O objeto no ponto $S$  envia raios de luz que incidem no espelho e são refletidos seguindo a **Lei da reflexão**, o que garante que, determinado um ponto $N$ por onde passa a reta normal ao espelho que também passa pelo ponto $S$, os triângulos $SNP$ e $S^\prime NP$ são iguais de modo que, do ponto de vista do observador, os raios de luz parecem ter se originado no ponto $S^\prime$ que aparenta estar "atrás do espelho" a mesma distância do ponto $N$ que o objeto real (Ponto $S$).

Desse modo, o olho vê uma imagem pontual exatamente da mesma maneira que veria um objeto pontual real colocado nessa posição, apesar disso, nenhum dos raio de luz que chega ao olho realmente vieram da parte de trás do espelho o que nos leva a definir que a imagem vista é **virtual**.

Apesar do exemplo mostrar um objeto pontual, o mesmo mecanismo ocorre para objetos maiores, afinal, cada ponto do objeto causa um efeito equivalente ao do exemplo, cada um com sua imagem na sua normal com o espelho a mesma distância da superfície para trás que o ponto do objeto real está para frente formando uma imagem virtual de mesma orientação e com **ampliação** unitária mas trocando a direita pela esquerda.

Sobre as imagens em espelhos planos concluímos então:
1. Se o objeto real está a uma distância de $p$ do espelho a sua imagem está uma distância $i$ para trás do espelho de tal modo que $p=-i$
2. Se o objeto real tem uma altura $h$ a sua imagem tem uma altura $h^\prime$ tal que $h= h^\prime$
3. A imagem tem a mesma orientação vertical que o objeto real mas horizontalmente a direita é trocada pela esquerda

# Formação de imagens em espelhos esféricos
Espelhos esféricos são espelhos construídos como partes de uma superfície esférica oca, podendo ser classificados como **Convexo** ou **Côncavo** com relação a um ponto $O$ a depender se o centro de curvatura $C$, centro da superfície esférica oca original, está do mesmo lado que esse ponto ou do lado oposto. Estabelecendo uma reta entre $O$ e $C$ no ponto em que essa reta cruza a superfície do espelho temos o vértice $V$.

Para tratar esses espelhos nos concentraremos em uma aproximação específica, chamada **aproximação para axial** ou **aproximação gaussiana** onde assumimos que o raio de curvatura $r$ é muito grande e que os ângulos de incidência no espelho são muito pequenos e pouco afastados do eixo central do espelho, de modo que os ângulos de reflexão são muito pequenos, isso para evitar o surgimento das chamadas aberrações esféricas.

Basicamente, ao incidir raios de luz em um espelho concavo o raios convergem para um ponto externo ao espelho chamado **foco** ou **ponto focal**, que nesse caso é dito **real**, por outro lado, num espelho convexo os raios divergem mas há uma convergência virtual dos seus prolongamentos no ponto focal que agora é chamado de ponto focal virtual.

Pode ser provado utilizando trigonometria e semelhança de triângulos que existe a seguinte relação entre a distância focal $f$ e o raio de curvatura $r$ dos espelhos:

$$f = \frac r 2$$


Note, para as definições que quando se trata de uma distância "para dentro do espelho", assumimos valores negativos.

Para considerar como um todo a formação de imagens em  espelhos esféricos, consideramos os raios principais:

1. Raio que incide no vértice $v$ do espelho $\to$ É refletido simetricamente com relação ao ao eixo central
2. Raio que incide alinhado com o centro de curvatura $C$ do espelho $\to$ É refletido de volta sobre o raio incidente (no sentido contrário)
3. Raio que incide paralelo ao eixo central $\to$ É refletido passando pelo foco $F$
4. Raio que incide alinhado com o foco $F$ do espelho $\to$ É refletido como um raio paralelo ao eixo central

A ressalva agora é a seguinte, a formação de imagens em espelhos esféricos permite certa deformação na altura da imagem que precisa ser considerada, para isso, existe uma fórmula extremamente útil que pode ser demonstrada a partir dessas considerações gerais desses raios principais aplicando trigonometria e semelhança de triângulos:


$$\frac{1}{p}+\frac 1 i= \frac 1 f $$

Ao utilizar essa equação devemos ter cuidado, no entanto, com os sinais dessas grandezas que devem obedecer as regras exibidas a seguir:

| Quantidade | Positiva (+)           | Negativa (-)           |
| ---------- | ---------------------- | ---------------------- |
| $p$        | Objeto real            | Objeto virtual         |
| $i$        | Imagem real            | Imagem virtual         |
| $h$        | Objeto direito         | Objeto invertido       |
| $h^\prime$ | Imagem direitra        | Imagem invertida       |
| $f$ e $r$  | Para espelhos côncavos | Para espelhos convexos |
| $m$        | Imagem direita         | Imagem invertida       |

A variável $m$, por sua vez, é o grau de ampliação do espelho, dado por:

$$m = \frac {h^\prime}h $$
