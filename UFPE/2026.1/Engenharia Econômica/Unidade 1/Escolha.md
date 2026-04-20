Agora vamos unir os conceitos que definimos de [[Restrição Orçamentária]], [[Preferências]] e [[Utilidade]], visando explicar o que o consumidor pode comprar e o que ele prefere comprar de maneira a, agora, explicar qual a cesta de bens que o consumidor irá escolher.

![[engec_017.png]]

Exibindo juntas a reta orçamentária e as curvas de indiferença iremos partir do pressuposto de que os consumidores escolhem sempre a cesta preferida do seu conjunto orçamentário o que pode ser interpretado com: Escolhem a cesta com maior utilidade dentro da sua restrição orçamentária.

Essa escolha, configura a chamada **escolha ótima**, na imagem, denotada por $(x_1^*, x_2^*)$ e perceba que esse ponto é justamente onde uma curva de indiferença tangencia a reta orçamentária e assim tem que ser, a curva de indiferença sobre a qual recai a escolha ótima não pode cruzar a reta orçamentária, então, a tangencia, exceto nos chamados **ótimos de fronteira**, como na imagem abaixo.

![[engec_018.png]]

Existem também gostos bizarros que não tem curvas de indiferença bem comportadas, mas não nos interessamos nesses casos, e também podemos nos restringir aos **ótimos interiores**, evitando lidar com os ótimos de fronteira.

Nesse caso, a curva de indiferença certamente tangenciará a reta orçamentária e no ponto ótimo suas inclinações devem ser iguais, apesar disso, a tangência não é uma condição suficiente para que um ponto seja uma escolha ótima, exceto no caso de curvas de indiferença estritamente convexas.

Como vimos, a inclinação da curva de indiferença, a $TMS$, se iguala a inclinação da reta orçamentária no ponto ótimo, mas conhecemos a inclinação dessa reta, então, no ponto ótimo é verdade que:

$$TMS = -\dfrac{p_1}{p_2}$$

E sempre que a TMS diferir da razão de preços, o consumidor não poderá estar em seu ponto ótimo de escolha.

A escolha ótima dos bens $1$ e $2$ num determinado conjunto de preços e de renda é chamada de **cesta demandada**, de forma que, em geral, ao variar os preços dos itens, variamos também essa escolha ótima. Definimos então a função [[Oferta e demanda#Demanda|demanda]] como a função que relaciona a escolha ótima, isto é, as quantidades demandadas 

# Substitutos perfeitos
No caso de substitutos perfeitos as escolhas ótimas serão sempre ou uma das fronteiras, isto é, os interceptos vertical ou horizontal da reta orçamentária ou a reta orçamentária inteira. Isso é lógico se você pensar um pouco, afinal, se os bens são substitutos perfeitos o consumidor irá preferir sempre o mais barato ou, no caso de ambos terem o mesmo preço, será indiferente a qualquer cesta na reta orçamentária.

$$
x_1 = 
\begin{cases}
m/p_1 \ \ \ \text{ se } \ \ \  p_2 > p_1 \\
\\
\text{Qualquer número entre 0 e } m/p_1 \ \ \ \text{ se } \ \ \  p_2 = p_1 \\
\\
0 \ \ \ \text{ se } \ \ \  p_2 < p_1 \\
\end{cases}
$$

# Complementares perfeitos
Para os complementares perfeitos o consumidor quer sempre comprar em proporções fixas, assim sendo, o que procuramos é o ponto da reta orçamentária onde é possível comprar a maior quantidade de itens seguindo a proporção pré-estabelecida, já que caso contrário, isto é, se aumentássemos a quantidade de items sem seguir a proporção isso aumentaria o preço da cesta em aumentar sua utilidade, nesse caso:

$$p_1x + p_2x = m \implies x_1 = x_2 = \dfrac{m}{p_1 + p_2}$$

# Males e Neutros
Para os males e os bens neutros, a questão é que o consumidor irá tender a gastar sempre mais com o bem que não se enquadra nessa classificação, já que uma maior quantidade de um male diminui a utilidade da cesta e uma maior quantidade de um bem neutro não afeta a utilidade da cesta.

# Cobb-Douglas
Usando [[Cálculo 2|cálculo]] podemos derivar a função demanda da preferência Cobb-Douglas como sendo:

$$x_1 = \dfrac{c}{c+ d}\cdot\dfrac{m}{p_1}$$
$$
x_2 = \dfrac{d}{c+d}\cdot\dfrac{m}{p_2}
$$

Algo interessante dessa função é que você pode mensurar a fração da renda total que o consumidor consome de um bem da seguinte maneira: 

Se ele consome $x_1$ do bem $1$ a um preço $p_1$ a fração consumida da renda total é simplesmente:

$$\dfrac{x_1p_1}{m} =\dfrac{c}{c+ d}\cdot\dfrac{m}{p_1}\cdot \dfrac{p_1}{m} = \dfrac{c}{c+d}$$

Ou para o item $2$:

$$\dfrac{x_2p_2}{m} = \dfrac{d}{c+ d}\cdot\dfrac{m}{p_2}\cdot \dfrac{p_2}{m} = \dfrac{d}{c+d}$$

De forma que o consumidor gasta sempre proporções fixas da sua renda com cada bem e sendo assim é conveniente escolher sempre expoentes para a função Cobb-Douglas que satisfaçam:

$$u(x_1,x_2) = x_1^\alpha x_2^{1-\alpha}$$

Assim, podemos interpretar $\alpha$ como a fração da renda gasta com o item $x_1$ e interpretar $1-\alpha$ como a fração gasta com $x_2$.