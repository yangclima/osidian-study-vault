Queremos definir as integrais no plano complexo, que, em geral, se parecem muito com as [[Integrais de linha]], o que nos leva a revisitar o conceito de curva e de [[Parametrização de curvas]], dessa vez com curvas no plano complexo, parametrizadas com um parâmetro $t$ de tal modo que:

$$z(t) = x(t) + iy(t); \ a \leq t \leq b$$

Caso em que denominamos o ponto $(x(a),y(a))$ por **ponto inicial** da curva e o ponto $(x(b), y(b))$ por **ponto final, ou terminal**, da curva, valem também as seguintes classificações para as curvas:

1. **Suave:** Uma curva $C$ no [[O plano complexo|plano complexo]] é **suave** se a sua parametrização $z(t)$ é tal que sua [[Diferenciabilidade e Analiticidade|derivada]] $z^\prime(t)$ é não nula em todos os pontos do intervalo $[a,b]$.
2. **Suave por partes:** Uma curva $C$  é **Suave por partes** se ela puder ser divida em curvas $n$ curvas $C_1, C_2, \cdots, C_n$ de tal modo que cada uma dessas partições seja individualmente suaves, nesse caso, a chamamos de **caminho**, **percurso** ou **contorno**
3. **Simples:** Uma curva $C$ é simples se para todos os pontos $t_1 \neq t_2$, $z(t_1) \neq z(t_2)$, exceto talvez, para $t_1 = a$ e $t_2 = b$
4. **Fechada:** Uma curva $C$ é fechada se $z(a) = z(b)$
5. **Fechada simples:** Uma curva $C$ é fechada simples se $z(a) = z(b)$ e para quaisquer outros valores $t_1 \neq t_2$, $z_1 \neq z_2$.

Além disso, é relevante para as definições que tomaremos a seguir, que tomemos por convenção a **Orientação positiva** de uma curva como sendo a orientação tal que uma pessoa percorrendo a curva tenha sempre o seu interior à esquerda, ou de forma similar, dizemos que uma curva $C$ tem sentido positivo se este sentido corresponde a valores crescentes do parâmetro $t$ de sua parametrização, o **sentido negativo** é definido então como o inverso do positivo e é denotado por $-C$, a **curva oposta** de $C$.

# Integral de uma função de valor complexo
O caso mais simples de integral complexa é a **integral de uma função de valor complexo de uma variável real**, isto é, digamos que $f(t) = f_1(t) + if_2(t)$, nesse caso, podemos integrar a função utilizando apenas integrais reais, definindo então a **integral da função de valor complexo** $f(t)$:

$$\int_a^bf(t)dt = \int_a^bf_1(t)dt + i\int_a^bf_2(t)dt $$

De modo que se $f_1$ e $f_2$ são contínuas no intervalo $[a,b]$ as partes real e imaginária da integral acima estão definidas e portanto a integral de $f(t)$ também está e valem para ela todas as propriedades de uma integral real.
# Integral de contorno
Agora queremos calcular a integral de linha, aqui chamada de integral de contorno, de uma [[Funções Complexas|função complexa]] qualquer $f(z)$ sob uma curva $C$ qualquer, ou seja:

$$\int_Cf(z)dz$$

Se separarmos $f(z)$ em suas partes real e complexa com $f(z) = u +iv$ e o diferencial $dz$ como $dz = dx + idy$ encontraremos então:

$$
\int_Cf(z)\,dz = \int_C(u+iv)(dx+idy) = \int_Cu\,dx-v\,dy + i\int_Cv\,dx + udy 
$$

Isto é, a integral de contorno de $f(z)$ sob a curva $C$ definida em termos de duas integrais reais, uma representando sua parte real e a outra sua parte imaginária, além disso, podemos obter que, se $f(z)$ for contínua em uma curva suave $C$ parametrizada por $z(t) = x(t)+iy(t); \ a \leq t \leq b$ então:

$$\int_C f(z)dz = \int_a^b f(z(t))z^\prime(t)dt $$

Calculada como a Integral de uma função de valor complexo, já que o seu integrando $f(z(t))z^\prime(t)$ é uma função desse tipo.

A integral de contorno se parece muito com as integrais de linha e preserva as suas propriedades.