Como vimos, alguns estudiosos definem e dividem o [[O que é cálculo|cálculo]] como a ferramenta matemática utilizada para resolver dois problemas:
- O problema da tangente
- O problema da área
Por mais que essa definição seja muito limitada, ela nos ajuda a separar dois conceitos essenciais do cálculo: [[Derivada|As derivadas]] e [[Integral Indefinida|as integrais]].

# Integral definida e o problema da área
Desde a Grécia antiga, dezenas de estudiosos tentaram resolver o problema da área, basicamente, calcular a área de figuras complexas, até o século 17, o único método conhecido para fazer isso era muito complexo (O método da exaustão), até que desenvolveu-se o cálculo.

Bem, no nosso estudo, o problema da área pode ser sintetizado da seguinte forma: Calcular a área abaixo do gráfico de uma função num intervalo fechado definido $[a, b]$, ou seja, a área definida entre o eixo $x$, a curva $f(x)$ e as linhas $x = a$ e $x = b$, para isso podemos dividir o intervalo em $n$ partes e multiplicar o tamanho de cada parte por um valor que $f(x)$ assume em cada intervalo, ou seja, dividir essa área em $n$ retângulos, assim teríamos a área total definida a partir de (Usando a [[Notação sigma]]):
$$
\sum_{k=1}^{n} f(x^*_k) \Delta x_k
$$
Onde $x^*_k$ é um valor qualquer no k-ésimo intervalo e $\Delta x_k$ é o comprimento desse mesmo intervalo. Não é preciso pensar muito para perceber que existe um erro enorme nesse valor, porém, se dividirmos em partes cada vez menores o intervalo, esse erro será cada vez menor, e quando $\Delta x_k \rightarrow 0$ e consequentemente $n \rightarrow \infty$, a somatória é exatamente igual a área sob o gráfico, ou seja:
$$
\lim_{\Delta x_k \rightarrow 0} \sum_{k=1}^{n} f(x^*_k) \Delta x_k = A
$$
Bem, por simplicidade, Leibniz nos fez mais um favor, definindo uma notação para essas somas:
$$
\lim_{\Delta x_k \rightarrow 0} \sum_{k=1}^{n} f(x^*_k) \Delta x_k = \int_a^b f(x) dx
$$
Lê-se, a integral de $f(x)$ em função de $x$ no intervalo de $a$ a $b$. Chamamos $a$ e $b$ de limites de integração, $x$ de variável de integração e $f(x)$ de integrando.
