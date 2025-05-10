---
aula: 2
---
Para [[Funções de duas e três variáveis]], o [[Limite]], assim como para funções de 1 única variável independente, consiste no valor que a saída de uma função assume quando sua entrada se aproxima de um determinado ponto, esse valor pode ser denotado por:
$$
L = \lim_{(x,y) \rightarrow (a,b)}f(x,y)
$$
Lê-se "O limite de f de x quando (x,y) se aproxima de (a,b)", se o limite existir ele indica valor do qual a função se aproxima quando (x,y) está tão perto quanto quanto possível de (a,b), mas não é exatamente igual a (a,b), tanto que (a,b) não precisa fazer parte do domínio de f. 

Um ponto para se ter em mente é que para que o limite exista é preciso que a função se aproxime do valor por qualquer direção possível, no cálculo de variável única isso é determinado através de dois [[Limites Laterais]], porém, como aqui o domínio da função é o $\mathbb{R}²$ (Ou $\mathbb{R}³$) As forma de se aproximar de um ponto são infinitas, mesmo assim, prevalece a definição de que **se a função assume dois valores diferentes ao se aproximar de um ponto (a,b) por direções diferentes, então o limite não existe**.

Tendo isso em mente, é muito mais fácil provar que um limite NÃO EXISTE para uma função de duas variáveis do que provar que ele existe, isso pode ser feito fazendo a função se aproximar por caminhos simples de calcular:
- Ao longo do eixo $x$, congelando o valor de $y$ como $y = 0$
- Ao longo do eixo $y$, congelando o valor de $x$ como $x = 0$
- Ao longo da reta $y = x$
- Ao longo de uma reta arbitrária não vertical $y = mx$ (Se a função resultante ao aplicar essa aproximação é dependente de $m$ então o limite não existe)
- Ao longo da parábola $x = y^2$ 
Se todos esses caminhos de aproximação resultarem num mesmo limite, começamos a suspeitar que esse limite de fato existe, podemos provar a existência desse limite através de sua definição:
$$
\lim_{(x,y) \rightarrow (a,b)} f(x,y) = L \iff \text{Para todo } \epsilon > 0, \text{ se } (x,y) \in Dom(f) \text{ existe } \delta, \text{tal que:}
$$

$$
0 < \sqrt{(x-a)^2 + (y-b)^2 } < \delta \implies |f(x,y) - L| < \epsilon
$$
Manipulando essa definição procuramos argumentos e definições para provar que o limite existe.
# Propriedades 
Se $\lim_{(x,y) \rightarrow (a,b)} f(x,y) = L$ e $\lim_{(x,y) \rightarrow (a,b)} g(x,y) = M$, então:

1. $\lim_{(x,y) \rightarrow (a,b)} k \cdot f(x,y) = k \cdot \lim_{(x,y) \rightarrow (a,b)} f(x,y) = L$
2. $\lim_{(x,y) \rightarrow (a,b)} {[f(x,y) + g(x,y)]} = M + L$
3. $\lim_{(x,y) \rightarrow (a,b)} {[f(x,y) - g(x,y)]} = M - L$
4. $\lim_{(x,y) \rightarrow (a,b)} {[f(x,y) \cdot g(x,y)]} = M \cdot L$
5. $\lim_{(x,y) \rightarrow (a,b)} {\dfrac{f(x,y)}{g(x,y)}} = \dfrac{L}{M}, M \neq 0$ 
6. $\lim_{(x,y) \rightarrow (0,0)} f(x,y) = 0 \iff \lim_{(x,y) \rightarrow (0,0)} |f(x,y)|$
7. $\lim_{(x,y) \rightarrow (a,b)} f(x,y) \iff \lim_{(h,k) \rightarrow (0,0)} f(a + h,b + k)$
# Estendendo a definição
A mesma definição do limite de funções de duas variáveis pode ser estendida para funções de 3 ou mais variáveis:

$$
\lim_{(x,y,z) \rightarrow (a,b,c)} f(x,y,z) = L \iff \forall \epsilon > 0, \text{ se } (x,y,z) \in Dom(f) \text{ existe } \delta, \text{tal que:}
$$

$$
0 < \sqrt{(x-a)^2 + (y-b)^2 (z-c)^2} < \delta \implies |f(x,y,z) - L| < \epsilon
$$
# Continuidade
A continuidade, assim como para [[Função contínua|continuidade de funções de uma variável]] consiste na definição de que:
$$
\lim_{(x,y,z) \rightarrow (a,b,c)} f(x,y,z) = f(a,b,c)
$$
Isso implica que para uma função ser contínua num ponto $(a,b,c)$ ela precisa estar definida nesse ponto

OBS: Sempre tenha em mente que funções polinomiais são sempre contínuas e funções racionais de polinômios são sempre contínuas para todos os pontos para os quais estão definidas 

OBS: Se $f(x,y)$ é uma função contínua de duas variáveis e $g(x)$ é uma função de uma variável definida na imagem de $f$, a função $h = g \circ f$ definida por  $h = g(f(,x,y))$  também é contínua.