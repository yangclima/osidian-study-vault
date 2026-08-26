Quando nos deparamos com [[Equações Diferenciais]] ordinárias de segunda ordem não homogêneas cujo membro não pertence a nenhuma das classes de [[Função|funções]] para as quais podemos aplicar o [[Método dos Coeficientes Indeterminados]], podemos, de maneira geral, aplicar o método chamado de **Método da Variação dos Parâmetros** que fornece uma relação para encontrar soluções desse tipo de equação.

O principal ponto forte desse método é que ele é aplicável a qualquer EDO da forma:

$$y^{\prime\prime} + p(t)y^\prime + q(t)y = g(t)$$

Contudo, ele depende primeiro da nossa capacidade de encontrar as soluções da [[Soluções de Equações Lineares Homogêneas|equação diferencial homogênea associada]]:

$$y^{\prime\prime} + p(t)y^\prime + q(t)y = 0$$

E de resolver duas integrais que envolvem essas soluções e o membro da equação. Digamos que conhecemos a solução geral da EDO inicial e ela é:

$$Y_0(t) = C_1y_1(t) + C_2y_2(t)$$

Nesse caso, se $p(t)$, $q(t)$ e $g(t)$ são contínuas num intervalo aberto $I$, então, uma solução particular para a equação diferencial não homogênea é:

$$Y_1(t) = -y_1(t)\int \dfrac{y_2(t)g(t)}{W[y_1,y_2]}dt + y_2(t)\int \dfrac{y_1(t)g(t)}{W[y_1,y_2]}dt$$

Onde $W[y_1,y_2]$ é o Wronskiano das funções $y_1$ e $y_2$. De modo que a solução geral da EDO é:

$$Y(t) = Y_0(t) + Y_1(t) =$$
$$Y(t) = C_1y_1(t) + C_2y_2(t) -y_1(t)\int \dfrac{y_2(t)g(t)}{W[y_1,y_2]}dt + y_2(t)\int \dfrac{y_1(t)g(t)}{W[y_1,y_2]}dt$$

Aqui, as constantes de integração não importam e qualquer solução das integrais nos é suficiente.

