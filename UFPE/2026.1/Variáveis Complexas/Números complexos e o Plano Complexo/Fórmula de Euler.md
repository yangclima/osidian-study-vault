Usando a expansão em [[Séries de Taylor e Maclaurin]], o matemático Euler chegou a uma relação, muitas vezes dita como a mais linda da matemática, que conecta exponenciais, [[Números Complexos|o número complexo]], [[O plano complexo|coordenadas polares]] e as funções trigonométricas seno e cosseno através da seguinte relação:

$$
e^{i\theta} = \cos{(\theta)} + i\sin{(\theta)}
$$

Essa forma da equação pode ser entendida como a definição da exponencial complexa e pode-se, de maneira simples, provar que de fato, ela se comporta como uma verdadeira exponencial, isto é, sua [[Derivada]] toma-se da forma esperada, as propriedades da multiplicação e da divisão de exponenciais são válidas aqui bem como a decomposição dessa exponencial em séries de Taylor é equivalente a soma da decomposição em séries de Taylor do cosseno e do seno.

Daqui, surge a representação de um número complexo $z = x+yi$ na sua **forma polar**, já que, como $x = r\cos{\theta}$ e $y = r\sin{\theta}$ então, nesse caso:

$$
z = r\cos{(\theta)} + r\sin{(\theta)}i = r(\cos{\theta} + i\sin{\theta}) = re^{i\theta}
$$

E usando essa forma, todas as operações da [[Aritmética de números complexos]] continuam valendo:

1. $\arg{(z)} = \arg {(re^{i\theta})} = \theta$
2. $\overline z = \overline{re^{i\theta}} = re^{-i\theta}$
3. $|e^{i\theta}| = \sqrt{\sin^2{\theta} + \cos^2{\theta}} = 1 \implies |z| = |re^{i\theta}| = r$
4. $z_1z_2 = r_1e^{i\theta_1}\cdot r_2e^{i\theta_2} = r_1r_2e^{i(\theta_1 + \theta_2)}$
5. $\dfrac{z_1}{z_2} = \dfrac{r_1e^{i\theta_1}}{r_2e^{i\theta_2}} = \dfrac{r_1}{r_2}e^{i(\theta_1 - \theta_2)}$ 