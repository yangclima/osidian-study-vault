---
aula: 2
---
O [[Termodinâmica#Trabalho|trabalho]] e o [[Termodinâmica#O calor|calor]] não são exatamente grandezas, são processos, tanto que não é comum se referir a uma variação de trabalho $\Delta w$ e nem de calor $\Delta q$ (Essa segunda parece mais plausível, porém, é errado pensar dessa forma no calor), essa característica faz com que o trabalho e o calor não dependam do estado inicial e final do sistema, mas do caminho pelo qual o sistema passou, por exemplo, ao fazer uma expansão isotérmica de um mol de gás a temperatura de $298 K$ temos um trabalho de $w = -nRT\ln{(\dfrac{V_f}{V_i})} = -2,3 kJ$ para um volume variando de $8$ para $20$ litros, mas podemos fazê-lo chegar ao mesmo estado ($298K$ com volume de $20L$) por infinitos outros processos, como resfriá-lo a volume constante  e depois fazer uma expansão isobárica onde o trabalho seria menor e chegar ao mesmo estado, e esse é o grande problema.

A dependência que o trabalho e o calor tem do caminho que precisa ser percorrido faz com que seja difícil mensurar os seus valores em experimentos reais, mas felizmente, a relação que o trabalho tem com o calor faz com que a energia interna se comporte como o que chamamos de "Função de estado", ou seja, seu valor só depende do estado do sistema, da sua Pressão, Volume e Temperatura, no exemplo dado acima, portanto, a energia interna seria a mesma e como, ==para uma gás ideal qualquer variação à temperatura constante mantém a energia interna com nula==, no segundo processo teremos $\Delta U = 0$ e consequentemente $q = -w$, note que essa relação é verdadeira para qualquer processo onde $\Delta U = 0$. 
# Teorema da Equipartição 
O Teorema da equipartição, importantíssimo para a química, sobretudo para a termodinâmica relaciona a energia interna de uma gás com a sua temperatura enunciando que: O valor médio de cada contribuição quadrática para a energia de uma molécula em uma amostra na temperatura T é igual a $\dfrac{1}{2}k_BT$ o que nos permite relacionar a energia interna de um gás ideal como um função de sua temperatura, multiplicando essa contribuição pelo número de Avogadro $N_A$ que representa a quantidade de moléculas em um mol de gás ideal, temos que cada contribuição quadrática para a energia de uma amostra é de $U_m = n\dfrac{1}{2}RT$ (Já que $R = N_A \cdot k_B$), assim, para contribuições quadráticas temos: 3 contribuições rotacionais para qualquer gás, 0 contribuições rotacionais para moléculas monoatômicos, 2 contribuições rotacionais para moléculas lineares e 3 contribuições rotacionais para gases não lineares (Existem contribuições vibracionais e eletrônicas mas que podem ser ignoradas no contexto atual).

# Entalpia
A Entalpia é uma função de estado que pode ser utilizada para mensurar a quantidade de calor que entra ou sai de uma sistema numa reação ou expansão que ocorre em pressão constante, imagine que a volume constante todo o calor que entra no sistema se converte numa mudança de temperatura, porém, a a maioria das reações ocorrem em reatores abertos para a atmosfera, onde parte do calor será convertido numa expansão, assim, temos:
$$
H = U + PV
$$
 E consequentemente:
$$
\Delta H = \Delta U + PV
$$