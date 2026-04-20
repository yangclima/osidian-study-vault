Agora que conhecemos as [[Tecnologia|escolhas tecnológicas]] com que a empresa se depara, é hora de analisar como a empresa escolhe a quantidade que irá produzir e o método de produção que será utilizado, nesse caso, consideramos sempre que estamos num [[Os 10 Princípios da Economia#Princípio 6 Os Mercados são geralmente uma boa maneira de organizar a atividade econômica|mercado competitivo]] e que portanto cada empresa não tem, individualmente, influência sobre o preço de um insumo ou produto.

O **lucro econômico** $\pi$ de uma empresa que possui $n$ produtos e $m$ insumos é definido na seguinte equação:

$$\pi =\sum_{i=1}^np_iy_i- \sum_{i=1}^mw_ix_i $$

Onde $w_i$ é o preço do $i$-ésimo insumo $x_i$ e $p_i$ é o preço do $i$-ésimo produto, isto é, **receita menos custos**.

Aqui não levamos em consideração o custo de operação apenas, mas todo custo de oportunidade relacionado a todos os fatores de produção, por exemplo, o valor de aluguel das máquinas que não é ganho por que a empresa as aluga pra si mesmo.

# Fatores fixos e variáveis
Os fatores de produção de uma empresa podem pertencer a três categorias, os **fatores fixos**, **fatores quase fixos** e os **fatores variáveis**:

1. Fator fixo: O fator que precisa se empregado independente da empresa produzir ou não, por exemplo, os contratos de aluguel, mesmo que a empresa decida não produzir, tem que ser pagos
2. Fator Quase Fixo: São fatores que só precisam ser empregados se a empresa estiver produzindo e que representam valores fixos, por exemplo a energia elétrica para iluminação.
3. Fator variável: Fatores que podem ser empregados em quantidades variáveis.

# Maximização dos lucros de curto prazo
No curto prazo, se tivermos dois fatores de produção $x_1$ e $x_2$ de preços $w_1$ e $w_2$ para produzir um produto de preço $p$ e o fator de produção $x_2$  estiver fixo num valor de $\overline{x_2}$ só podemos variar $x_1$ e o nosso problema se torna maximizar a função:

$$\pi = pf(x_1,\overline{x_2}) - w_1x_1 - w_2\overline{x_2} \tag{1}$$

Nesse caso, o valor de $x_1$ que maximiza o lucro é $x_1^*$ e temos por definição que o produto do valor do produto pelo produto marginal no ponto ótimo tem d ser igual ao preço do insumo:

$$pPM_1(x_1^*,\overline{x_2}) = w_1$$

Já que se estivermos no lucro máximo da empresa, o aumento na produção devido ao aumento na quantidade do insumo $1$ deverá ser $0$, já que se for menor que $0$, o lucro poderia ser aumentado com uma diminuição na quantidade de $x_1$ e se fosse maior que zero, o lucro poderia ser aumentado, o mesmo resultado seria obtido realizando a maximização de $(1)$ com uma derivada em $x_1$.

A função $(1)$ pode ser reescrita, tomando $f(x_1,x_2) = 1$ de forma a obter a equação:

$$y = \dfrac{\pi}{p} + \dfrac{w_1}{p}x_1 + \dfrac{w_2}{p}\overline{x_2}$$

Que descreve as chamadas **Retas de isolucro**, retas no plano  $x_1\times\text{Produção}$ onde cada combinação de insumos gera uma quantidade fixa de lucro e para as quais os interceptos verticais que medem os lucros mais os custos fixos da produção

![[engec_021.png]]

Dessa forma a reta de isolucro mais alta é aquela que possui um maior lucro associado e então transicionamos para um caso parecido com a escolha ótima do consumidor, onde o objetivo é então encontrar o ponto da curva de produção que tangencia a reta de isolucro mais alta, onde a inclinação da curva de produção se iguala com a inclinação da reta de isolucro, isto é:

$$PM_1 = \dfrac{w_1}{p_1}$$

# Maximização do lucro no longo prazo
O problema de maximização do lucro no longo prazo é semelhante ao do curto prazo, com a diferença essencial de que aqui temos de lidar com variações em ambos os insumos, o que equivale a maximizar a função:

$$\pi = pf(x_1,x_2) -w_1x_1 -w_2x_2$$

Que equivale a encontrar os pontos tais que:

$$pPM_1(x_1^*,x_2^*) = w_1$$
$$pPM_2(x_1^*,x_2^*) = w_2$$