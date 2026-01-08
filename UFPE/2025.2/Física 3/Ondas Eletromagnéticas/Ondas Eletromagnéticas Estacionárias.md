Considere duas [[Ondas Eletromagnéticas Planas]] idênticas (Por simplicidade) se propagando em direções opostas, sendo o [[Campo Elétrico]] e [[Campo Magnético]] da primeira onda (Se propagando na direção $+ \hat i$ ) dados por:

$$
\begin{cases}
\vec E(x,t) = E_0\sin{(kx - \omega t)}\hat j \\
\vec B(x,y) = B_0\sin{(kx-\omega t)} \hat k
\end{cases}
$$

E os da segunda (Se propagando na direção $i \hat i$ ) dados por:

$$
\begin{cases}
\vec E(x,t) = E_0\sin{(kx + \omega t)}\hat j \\
\vec B(x,y) = -B_0\sin{(kx+\omega t)} \hat k
\end{cases}
$$

Aplicando aqui o **princípio da superposição**, podemos somar os campos de ambas as ondas obtendo então uma onda cujos campos são dados por:

$$
\begin{cases}
\vec E(x,t) = E_0( \sin{(kx - \omega t)} + \sin{(kx + \omega t)} ) \hat j \\
\vec B(x,y) = B_0( \sin{(kx-\omega t)} - \sin{(kx + \omega t)} )\hat k
\end{cases}
$$

Com a identidade trigonométrica do **seno da soma** ou seja:

$$
\sin{(\alpha \pm\beta)} = \sin{(\alpha)}\cos{(\beta)} \pm \sin{(\beta)}\cos{(\alpha)}
$$

podemos reescrever esses campos como:

$$
\begin{cases}
\vec E(x,t) = 2E_0\sin{(kx)}\cos{(\omega t)} \hat j \\
\vec B(x,y) = 2B_0\cos{(kx)}\sin{(\omega t)}\hat k
\end{cases}
$$

Percebemos que estas funções não possuem a forma de uma onda que se propaga, isto é, $f(x \pm vt)$, entretanto, elas satisfazem a equação de onda. Essa forma de função é que confere a essa onda o caráter **estacionário**, ou seja, a onda não se propaga, apenas varia no tempo e espaço dependendo de $x$ e $t$ e sendo então chamada de **Onda estacionária**.

Examinando as relações obtidas, vemos que, sempre que $\sin{(kx)} = 0$, o campo elétrico é nulo, independente do instante do tempo, chamamos os planos $x = a$ onde esse comportamento ocorre de **Planos nodais do campo elétrico** que ocorrem para os valores de $x$ dados por:

$$
kx = n\pi \implies x = \dfrac{n\pi}{k} = \dfrac{n\pi\lambda}{2\pi} = n\cdot \dfrac{\lambda}{2} \ \ \ \ \ \ n=0,1,2,3\cdots
$$

Além disso, para os valores onde $\sin{(kx)} = 1$ ocorre uma interferência construtiva entre as ondas e em dados instantes do tempo, o campo elétrico atinge sua máxima amplitude de $2E_0$ e chamamos os plano $x = a$ em que isso ocorre de **Planos antinodais do campo elétrico** que ocorrem para os valores de $x$ dados por:

$$
kx = (2n + 1)\dfrac{\pi}{2} \implies x = (2n + 1)\dfrac{\pi}{2k}  = (2n + 1)\cdot \dfrac{\lambda}{4} \ \ \ \ \ \ n=0,1,2,3\cdots
$$

Usando da mesma lógica, podemos obter que os **Planos nodais do campo magnético** ocorrem quando:

$$
x =(2n + 1)\cdot \dfrac{\lambda}{4} \ \ \ \ \ \ n=0,1,2,3\cdots
$$

Enquanto os **Planos antinodais do campo magnético** ocorrem quando:

$$
x = n\cdot \dfrac{\lambda}{2} \ \ \ \ \ \ n=0,1,2,3\cdots
$$

Quanto a dependência temporal da nossa **Onda estacionária** vemos que o campo elétrico é nulo quando $\cos(\omega t) = 0$, ou seja:

$$
\omega t = (2n+1)\dfrac{\pi}{2} \implies t = (2n+1)\cdot\dfrac{T}{4}
$$

Onde $T$ é o **período de oscilação**, assim, vemos que como a dependência temporal do campo magnético é $\sin(\omega t)$, então, quando o campo elétrico é nulo, o campo magnético é máximo, nesse caso, ao contrário das [[Ondas Eletromagnéticas Planas]] onde os campos estão em fase, nas ondas estacionárias eles estão defasados em $90\degree$.