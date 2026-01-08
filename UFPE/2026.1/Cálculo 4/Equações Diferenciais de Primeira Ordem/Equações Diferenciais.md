As leis do universo são escritas em linguagem matemática, isto é, a descrição matemática dos fenômenos é o que nos permite entender e prever os fenômenos da natureza, a ideia é simples, queremos relacionar grandezas através de equações.

Até certo ponto essas relações podem ser feitas usando da álgebra convencional, desde que as grandezas de interesse sejam estáticas, porém, os fenômenos mais interessantes da natureza envolvem a variação das grandezas físicas, sendo necessário então que a sua descrição seja feita através de equações especiais que relacionam tanto grandezas estáticas quanto taxas de variação dessas grandezas.

Como a [[Derivada]] de uma função pode ser interpretada justamente como a taxa de variação instantânea de uma função, ou seja, $\dfrac{dx}{dt}$  pode ser interpretada como a taxa na qual a quantidade variável $x$ está mudando com relação a variável independente $t$ é de se esperar que as derivadas apareçam nesse tipo especial de equações que estamos buscando e de fato aparecem, essas tais equações recebem o nome de **Equações diferenciais**.

---------------------

**Definição:** Uma equação que relaciona uma função desconhecida e uma ou mais de suas derivadas é denominada **Equação Diferencial**.

-----

Entender que essas equação relacionam funções ao invés de valores é crucial para o seu entendimento, perceba: Enquanto na álgebra convencional procuramos valores que satisfaçam uma equação, aqui, procuramos funções que o façam, isto é, funções que se comportem como determina a tal Equação Diferencial.

Vamos a um exemplo, a equação diferencial definida por: $\dfrac{dy}{dx} = 2xy$ é satisfeita pela função $y(x) = e^{x^2}$, logo, essa função é uma solução para esta equação diferencial.

Note, entretanto, que na verdade, qualquer função da forma $y(x) = Ce^{x^2}$ onde $C$ é uma constante, é também solução para essa equação, este é um ponto notável a respeito das equações diferenciais, suas soluções não são uma função propriamente dita, mas uma família de funções, entretanto, a maioria das equações diferenciais está relacionada a uma modelagem matemática de algum fenômeno, assim, deve existir uma resposta correta para a resolução dessas equações, e de fato, quando fixamos um **valor inicial**, por exemplo $f(a) = b$, especificamos uma solução específica para o nosso problema.

No nosso exemplo, usamos apenas a primeira derivada da função, mas essas equações podem ficar muito mais complexas e envolver várias [[Derivadas de Ordem Superior]] da função, assim, podemos classificar as equações diferenciais de acordo com a ordem de sua derivada, a equação no nosso exemplo pode ser então chamada de **equação diferencial de primeira ordem** já que envolve apenas a primeira derivada da função, na mesma medida que um equação que envolve a n-ésima derivada da função é chamada então de **equação diferencial de n-ésima ordem**, cuja forma mais normal é:

$$
F(x,y,y^\prime, y^{\prime\prime}, \cdots, y^{(n)}) = 0
$$

Um problema comum que pode surgir é a definição implícita de funções, um exemplo é o surgimento de uma derivada elevada ao quadrado ou uma mesma derivada com diferentes coeficientes polinomiais na mesma equação o que impõe certas dificuldades a sua resolução, assim, chamamos de **equação diferencial na forma normal** as equações diferenciais que podem ser resolvidas explicitamente para a sua derivada de maior ordem, ou seja, pode ser escrita na forma:

$$
y^{(n)} = F(x,y,y^\prime, y^{\prime\prime}, \cdots, y^{(n-1)})
$$

Você deve imaginar que, assim como fizemos no cálculo multivariável ao lidar com funções de múltiplas variáveis independentes, podemos ter equações que conectem múltiplas funções de variáveis independentes diferentes, bem como suas derivadas, de fato isso ocorre e aqui passamos a envolver [[Derivadas parciais]] em nossa equações, o que nos leva a uma nova classificação, equações diferenciais com uma única variável independente são chamadas de **equações diferenciais ordinárias** enquanto as com múltiplas variáveis independentes são chamadas de **equações diferenciais parciais**.

Agora que conhecemos as equações diferenciais e sua classificação, a próxima pergunta é: Tendo uma equação diferencial e sabendo que ela possui solução que satisfaz uma condição inicial fixada, como encontrar tal solução?

