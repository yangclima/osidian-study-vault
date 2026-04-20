Começaremos nosso estudo sobre o comportamento das empresas e o primeiro passo, tal qual fizemos para o consumidor é discorrer sobre as restrições impostas ao seu comportamento pelos seus clientes, concorrentes e a natureza que impões a restrição de que só há algumas formas viáveis de produzir a partir dos insumos.

Essa teoria é muito mais simples que a do consumidor, já que a [[Utilidade]] que é o parâmetro que usamos no caso do consumidor não é observável, ao contrário do caso atual, onde podemos comparar as quantidades produzidas.

Os insumos utilizados na produção são divididos em várias categorias tais como terra, trabalho, capital e matéria prima. Enquanto os outros termos são primitivas, os Bens de Capital são um termo novo que se refere aos insumos de produção que são também bens produzidos, para evitar a confusão com o termo Capital Financeiro, chamaremos estes fatores de produção de Capital Físico.

A natureza impõe restrições tecnológicas a produção de modo que apenas algumas combinações de insumos constituem combinações viáveis de produzir certa quantidade de produto.

Isso limita as empresas a alguns planos de produção que podem ser descritos pela listagem de todas as combinações de insumos e produtos tecnologicamente factíveis, onde seu conjunto é chamado de **conjunto de produção**.

Suponhamos, por exemplo, que temos apenas um insumo, medido por $x$, e um produto, medido por $y$ e dizer que determinado ponto $(x, y)$ se encontra no conjunto de produção significa que é tecnologicamente viável produzir uma quantidade $y$ de produto com a utilização de uma quantidade $x$ de insumo.

Como os insumos tem um custo, faz sentido nos limitarmos a análise do **máximo possível de produção** que se possa obter com dada quantidade de insumo, esse máximo ocorre na fronteira do conjunto produção que é dada pela chamada **função de produção**

![[engec_020.png]]

Esse conceito também se aplica ao caso onde temos mais de um insumo, nesse caso, a função produção, digamos, $f(x_1,y_1)$ mediria a quantidade máxima de produção que poderia ser atingida com $x_1$ unidades do insumo $1$ e $x_2$ unidade do insumo $2$.

No caso onde temos dois insumos, temos as chamadas isoquantas, um conceito parecido com a ideia de [[Preferências|curvas de indiferença]] e que representam todas as combinações dos dois insumos que são suficientes para produzir uma determinada quantidade de produto sendo rotuladas de acordo com isso e possuindo caráter realístico e fundamentado.

Alguns exemplos de tecnologia são então:

# Proporções fixas
Esse é o caso onde os insumos precisam estar em proporções fixas para produzir um produto, de forma parecida com o dos bens complementares perfeitos da teoria do consumidor, nesse caso, a função de produção é:

$$f(x_1,x_2) = \min\{x_1,x_2\}$$

# Substitutos Perfeitos
Esse é o caso onde os insumos são inter substituíveis, de forma que não importa a quantidade individual de insumo mas a quantidade total dos insumos em conjunto, assim, sua função de produção é:

$$f(x_1,x_2) = x_1 + x_2 $$

# Cobb-Douglas
Assim como temos nas curvas de indiferença o perfil Cobb-Douglas podemos definir aqui a função de produção Cobb-Douglas, que possui um formato muito parecido:

$$f(x_1,x_2) = Ax_1^ax_2^b$$

A adição do $A$ é oriunda da natureza da função de produção que possui um valor concreto, diferente da utilidade, assim o $A$ se torna não arbitrário e passar a representar um fator de escala da produção, enquanto as constantes $a$ e $b$ representam a dependência da produção com relação a cada insumo.

# Produto Marginal
Assim como definimos a utilidade marginal podemos então definir o **produto marginal**, uma medida da resposta da função de produção a uma variação na quantidade de um insumo, ou seja, algo como a quantidade adicional de produto por unidade adicional de insumo, por exemplo, para o item $1$:

$$PM_1 = \frac{\Delta y}{\Delta x_1} = \frac{f(x_1 + \Delta x_1, x_2)-f(x_1, x_2)}{\Delta x_1}$$

E para o produto marginal do insumo $2$:

$$
PM_2 = \frac{\Delta y}{\Delta x_2} = \frac{f(x_1 , x_2+ \Delta x_2)-f(x_1, x_2)}{\Delta x_2}
$$

E então definimos em termos dessas taxas a variação da produção:

$$\Delta y = PM_1\Delta x_1 + PM_2\Delta x_2$$

E da mesma forma que pensamos na $TMS$ como uma taxa de troca, definimos a $TTS$, **taxa técnica de substituição** como a taxa de troca entre os insumos mantendo a a produção na mesma isoquanta, algo como, quantas unidades do insumo $1$ eu preciso para substituir uma determinada quantidade do insumo $2$ e é definida como:

$$TTS = \dfrac{\Delta x_2}{\Delta x_1} = -\dfrac{PM_1}{PM_2}$$

# $PM$ e $TTS$ Decrescente
Existe, em questões relacionadas a análise dessas curvas de produção a chamada **Lei do produto marginal decrescente**, que não configura de fato uma lei mas é uma observação válida e muito comum a maioria dos sistemas de produção, e define que, ao manter a quantidade de um insumo constante e aumentar a quantidade do outro, você tem rendimentos decrescentes, cada aumento sucessivo influenciará cada vez menos na quantidade de produto, como se a produção se tornasse limitada pelo outro insumo, é fácil ver a validade dessa argumento ao pensar, por exemplo, um insumo como a quantidade de terra e o outro como a quantidade de trabalhadores.

Da mesma maneira, outro pressuposto é a $TTS$ decrescente, que define que ao se manter na mesma isoquanta e aumentar a quantidade do insumo $1$, temos uma diminuição na taxa técnica de substituição e ao se manter na mesma isoquanta e aumentar a quantidade do insumo $2$, devemos ter um aumento na $TTS$, uma observação fácil de visualizar geometricamente e nos exibe a natureza convexa dessas curvas.

# Curto e Longo Prazo
É importante, ao analisar a função de produção, estar ciente de distinções importantes a respeito do curto e longo prazo, no curto prazo, alguns insumos são fixos, devido ao fato de que num período de tempo pequeno, não há possibilidade de aumentar essa quantidade, por exemplo, o número de fábricas, por outro lado, no longo prazo, todos os insumos devem variar e essa análise é essencial.

# Rendimentos de Escala
A última análise que introduziremos é a dos rendimentos de escala, que consiste em analisar os rendimentos ao escalar um processo de produção, isto é, ao aumentar juntos os insumos de produção por um fator constante $t$, assim, temos três casos possíveis:

1. **Rendimento constante de escala:** Esse é o mais comum e descreve os casos onde ao multiplicar por $t$ as quantidades de cada insumo temos um rendimento $t$ vezes maior, isto é, proporcional a escala dos insumos, ou seja: $$f(tx_1,tx_2) = tf(x_1,x_2)$$
2. **Rendimento crescente de escala:** Esse tipo de rendimento ocorre quando um aumento nas quantidades de insumo gera um aumento proporcionalmente maior na produção, geralmente esse rendimento surge apenas em determinadas faixas de escala e é descrito por: $$f(tx_1,tx_2) > tf(x_1,x_2)\,; \ t > 1$$
3. **Retorno decrescente de escala:** Esse tipo de rendimento vai contra o censo comum e geralmente ocorre apenas quando esquecemos de levar em conta algum insumo e consiste no caso em que uma aumento nas quantidades de insumo gera um aumento proporcionalmente menor na quantidade produzida endo então descrito por: $$f(tx_1,tx_2) < tf(x_1,x_2)\,; \ t > 1$$
