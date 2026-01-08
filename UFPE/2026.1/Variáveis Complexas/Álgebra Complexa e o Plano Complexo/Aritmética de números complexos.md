Como vimos, os [[Números Complexos]] são definidos como o conjunto $\mathbb{C}$ de todos os números $z = x+ yi$ onde $x,y \in \mathbb{R}$. O número $x$, parte real de $z$ também pode ser denotado por $\Re{(z)}$ ou $Re(z)$ e o número $y$, parte imaginária de $z$ pode ser denotado por $\Im(z)$ ou $Im(z)$.

Podemos definir então as operações básicas entre número complexos:
# Adição
Sendo os números complexos $z_1 = x_1 + y_1i$ e $z_2 = x_2 + y_2i$ definimos a operação de adição entre $z_1$ e $z_2$ como:

$$
z_1 + z_2 = (x_1 + x_2) + (y_1+y_2)i
$$
# Subtração
Sendo os números complexos $z_1 = x_1 + y_1i$ e $z_2 = x_2 + y_2i$ definimos a operação de subtração entre $z_1$ e $z_2$ como:

$$
z_1 - z_2 = (x_1 - x_2) + (y_1 - y_2)i
$$
# Multiplicação
Sendo os números complexos $z_1 = x_1 + y_1i$ e $z_2 = x_2 + y_2i$ definimos a operação de multiplicação entre $z_1$ e $z_2$ como:

$$
z_1 \cdot z_2 = (x_1 + y_1i)\cdot(x_2 + y_2i) = (x_1\cdot x_2 - y_1\cdot y_2) + (x_1\cdot y_2 + x_2\cdot y_1)i
$$
# Conjugação 
Agora, definiremos uma nova operação, especial para os números complexos e que opera sobre um único número por vez. Seja  um número complexo qualquer $z = x + yi$, chamamos de **conjugado de $z$** e denotamos por $\overline{z}$ o número:

$$
\overline{z} = x - yi
$$

Perceba que a ideia é basicamente inverter o sinal da parte imaginária de $z$, essa nova operação será útil para definir alguns outros conceitos relacionados aos números complexos.
# Divisão
Agora que temos a operação de conjugação, podemos definir com mais facilidade a forma como podemos realizar a divisão de dois números complexos. Dados dois números $z_1 = x_1+y_1i$ e $z_2 = x_2+y_2i$ a divisão de $z_1$ por $z_2$ é dada por:

$$
\dfrac{z_1}{z_2} = \dfrac{z_1}{z_2}\cdot\dfrac{\overline{z_2}}{\overline{z_2}} = \dfrac{x_1+y_1i}{x_2+y_2i} \cdot \dfrac{x_2-y_2i}{x_2-y_2i} = \dfrac{(x_1\cdot x_2 + y_1\cdot y_2) + (y_1\cdot x_2-x_1\cdot y_2)i}{x_2^2+y_2^2}
$$

Perceba que multiplicamos tanto o numerador quando denominador pelo conjugado do divisor $\overline z_2$ o que não altera a divisão, mas permite lidar com a unidade imaginária $i$ apenas no numerador.
# Magnitude
Assim como o conjugado é uma propriedade de um número complexo, a magnitude também o é, no próximo capítulos veremos por que faz sentido  falar em magnitude de um número complexo. Dado um número complexo qualquer $z = x +yi$, a sua magnitude $|z|$, também chamada de módulo ou comprimento de $z$ é definida como:

$$
|z| = \sqrt {z\cdot\overline z} = \sqrt{x^2 + y^2}
$$

Perceba que essa raiz não inclui o número $i$ e é portanto sempre positiva.
