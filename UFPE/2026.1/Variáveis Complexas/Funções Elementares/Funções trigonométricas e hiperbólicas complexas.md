# Funções trigonométricas complexas
Se $x$ for uma variável real, sabemos que a [[Funções Exponencial e Logarítmica Complexas#Função exponencial Complexa|função exponencial]] nos dá:

$$e^{ix} = \cos{(x)} + i\sin{(x)} \ \ \ \text{e} \ \ \ e^{-ix} = \cos{(x)} - i\sin{(x)}$$

Então, a partir dessas duas equações, podemos escrever:

$$\cos{(x)} = \dfrac{e^{ix} + e^{-ix}}{2}$$
$$\sin{(x)} = \dfrac{e^{ix} - e^{-ix}}{2i}$$

Dessa forma, não há impedimento algum em substituir $x$ por uma [[Números Complexos|variável complexa]] de tal maneira que podemos definir as [[Funções Complexas|funções]] seno e cosseno complexas como:

$$\cos{(z)} = \dfrac{e^{iz} + e^{-iz}}{2}$$
$$\sin{(z)} = \dfrac{e^{iz} - e^{-iz}}{2i}$$

De tal forma que se a parte imaginária de $z$ for nula, teremos normalmente as funções seno e cosseno reais, além disso, podemos definir todas as outras funções trigonométricas, tangente, secante, cossecante e cotangente.

E além de tudo as identidades trigonométricas clássicas também funcionam aqui, de modo que:

$$\sin{(-z)} = -\sin{(z)} \ \ \ \text{e} \ \ \ \cos{(-z)}=\cos{(z)}$$
$$\cos^2{(z)}+ \sin^2{(z)} = 1$$
$$\sin{(z_1 \pm z_2)} = \sin{(z_1)}\cos{(z_2)} \pm \sin{(z_2)}\cos{(z_1)}$$
$$\cos{(z_1 \pm z_2)} = \cos{(z_1)}\cos{(z_2)} \mp \sin{(z_2)}\sin{(z_1)}$$

Apesar disso, em geral, a desigualdades que envolvem funções trigonométricas não se preservam, por exemplo, o cosseno de um número complexo pode ser maior que 1, ao contrário do cosseno de um número real.

Quanto a periodicidade das funções trigonométricas, elas se preservam, inclusive seu período, o que era de se esperar já que a exponencial complexa é por si própria uma função periódica.

Um outro tópico interessante é sobre as equações que envolvem essas funções trigonométricas, que podem ser trabalhadas de forma mais fácil se reescrevemos as funções seno e cosseno em termos da partes real e imaginária de $z$, onde obteremos as funções trigonométricas em termos dessas componentes:

$$\sin{(z)} = \sin{(x)}\cosh{(y)}+i\sinh{(y)}\cos{(x)}$$
$$\cos{(z)} = \cos{(x)}\cosh{(y)} - i\sin{(x)}\sinh{(y)}$$


Podemos ainda usar essas fórmulas para obter equações para o módulo dessas [[Funções Complexas]]:

$$|\sin{(z)}| = \sqrt{\sin^2{(x)}+\sinh^2{(y)}}$$
$$|\cos{(z)}| = \sqrt{\cos^2{(x)}+\sinh^2{(y)}}$$

Um ponto interessante que pode ser mostrado pela equação acima é que aqui, diferente do que ocorre para as funções seno e cosseno reais, o cosseno e seno complexos são funções ilimitadas.

Além disso, usando essas equações podemos ainda mostrar que os zeros das funções seno e cosseno complexos são os mesmos que para suas versões reais e que não há zeros adicionais no [[O plano complexo|plano complexo]].

Quanto a [[Diferenciabilidade e Analiticidade]], tanto a função seno quando a cosseno são inteiras no plano complexo e portanto deriváveis em todos os pontos e suas derivadas coincidem com as derivadas das suas equivalentes reais.

# Funções Hiperbólicas Complexas
As funções seno e cosseno hiperbólicas reais são definidas como:

$$\sinh{(x)} = \dfrac{e^x - e^{-x}}{2} \ \ \ \text{e} \ \ \ \cosh{(x)} = \dfrac{e^x+ e^{-x}}{2}$$

Então, substituindo por uma variável complexa, obtemos:

$$\sinh{(z)} = \dfrac{e^z - e^{-z}}{2} \ \ \ \text{e} \ \ \ \cosh{(x)} = \dfrac{e^z+ e^{-z}}{2}$$

Essas funções, no entanto, diferente das suas versões reais, possuem infinitos zeros que são puramente imaginários.

Além disso, essas funções, até pela própria definição, são funções inteiras e suas derivadas funcionam da mesma maneira que as derivadas da suas versões reais. 

Um fato interessante, no entanto, é que não existem relações simples entre as versões reais do seno e cosseno com suas versões hiperbólicas, relação que nos números complexos surge naturalmente e nos dá:

$$\sin{(z)} = -i\sinh{(iz)} \ \ \ \text{e} \ \ \ \cos{(z)} = \cosh{(iz)}$$
$$\sinh{(z)} = -i\sin{(iz)} \ \ \ \text{e} \ \ \ \cosh{(z)} = \cos{(iz)}$$

E podemos inclusive usar essas relações para deduzir as seguintes propriedades das funções trigonométricas hiperbólicas:

$$\sinh{(-z)}= -\sinh{(z)} \ \ \ \text{e} \ \ \ \cosh{(-z)} = \cosh{(z)}$$
$$\sinh^2{(z)} - \cosh^2{(z)} = 1$$
$$\sinh{(z_1 \pm z_2)}= \sinh{(z_1)}\cosh{(z_2)} \pm \sinh{(z_2)}\cosh{(z_1)}$$
$$\cosh{(z_1 \pm z_2)}= \cosh{(z_1)}\cosh{(z_2)} \pm \sinh{(z_2)}\sinh{(z_1)}$$