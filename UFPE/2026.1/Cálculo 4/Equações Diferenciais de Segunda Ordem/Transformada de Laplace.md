Nos problemas que envolvem [[Equações Diferenciais]] na engenharia, muitas vezes é pouco prático utilizar os métodos que vimos até aqui para resolver essas equações, um método especialmente adequado para esses problemas, baseia-se na chamada **Transformada de Laplace**. 

Uma **Transformada Integral** é uma relação da forma:

$$F(s) = \int_\alpha^\beta K(s,t)f(t)dt$$

Onde $K(s,t)$ é uma [[Função|função]] dada chamada de **Núcleo da Transformação** e os limites $\alpha$ e $\beta$ também são dados, de forma que essa relação transforma a função $f(t)$ em uma função $F(s)$ chamada de **transformada de $f$**.

Em específico, a transformada de Laplace, denotada por $F(s)$ ou $\mathcal{L}\{f(t)\}$ e se define como:

Supondo que $f(t)$ é uma função definida para $t\geq 0$ que é **Seccionalmente Contínua**, ou seja, contínua por partes em $t\geq 0$ e de **Ordem exponencial**, isto é, existem constantes reais $K > 0$, $M > 0$ e $\alpha$, tal que $|f(t)|\leq Ke^{\alpha t}$ quando $t\geq M$ então, para $s>\alpha$:

$$\mathcal{L}\{f(t)\} = F(s) = \int_0^\infty e^{-st}f(t)dt$$

Então essa transformada é definida por essa equação sempre que essa integral convergir, o que ocorre quando existe:

$$\lim_{A\to\infty} \int_0^Ae^{-st}f(t)dt$$

O grande poder dessa transformada só é destravado quando generalizamos para um $s$ [[Números Complexos|complexo]] mas em [[Cálculo 4]] não lidaremos com isso.

As Transformadas de Laplace para as principais funções estão descritas na seguinte tabela:

| **Função**        | **Transformada de Laplace**      | **Domínio**      |
| ----------------- | -------------------------------- | ---------------- |
| $1$               | $\dfrac{1}{s}$                   | $s > 0$          |
| $e^{\alpha t}$    | $\dfrac{1}{s-\alpha}$            | $s > a$          |
| $t^n$             | $\dfrac{n!}{s^{n+1}}$            | $s > 0$          |
| $\sin{\alpha t}$  | $\dfrac{\alpha}{s^2 + \alpha^2}$ | $s > 0$          |
| $\cos{\alpha t}$  | $\dfrac{s}{s^2 + \alpha^2}$      | $s> 0$           |
| $\sinh{\alpha t}$ | $\dfrac{\alpha}{s^2 - \alpha^2}$ | $s> \|\alpha\|$  |
| $\cosh{\alpha t}$ | $\dfrac{s}{s^2 - \alpha^2}$      | $s > \|\alpha\|$ |

E uma propriedade importante é a linearidade dessa transformada, isto é, valem as propriedades:

1. $\mathcal{L}\{f(t) + g(t)\} = \mathcal{L}\{f(t)\}+\mathcal{L}\{g(t)\}$ 
2. $\mathcal{L}\{\lambda f(t)\} = \lambda\mathcal{L}\{f(t)\}$


Podemos ainda escrever a transformada da derivada de uma função $f$ contínua para a qual sua derivada $f^\prime$ é seccionalmente contínua e de ordem exponencial como:

$$\mathcal{L}\{f^\prime(t)\} = s\mathcal{L}\{f(t)\} - f(0)$$

Além disso, se as mesmas condições são satisfeitas entre $f^\prime$ e $f^{\prime\prime}$ temos:

$$\mathcal{L}\{f^{\prime\prime}(t)\} = s^2\mathcal{L}\{f(t)\} - f(0) - f^\prime(0)$$

Em alguns casos é ainda útil definir a chamada **Transformada de Laplace Inversa**:

$$\mathcal{L}^{-1}\{F(s)\} = f(t) \implies \mathcal{L}\{f(t)\} = F(s)$$

Que também é linear e será útil para a resolução de EDO's usando a transformada de Laplace.