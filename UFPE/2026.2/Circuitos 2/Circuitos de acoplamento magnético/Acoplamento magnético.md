A maioria dos circuitos tem o chamado acoplamento condutivo, componentes adjacentes afetam um ao outro através da efetiva condução de eletricidade, existem porém, um outro tipo de acoplamento chamado **Acoplamento magnético** através do qual componentes adjacentes podem interagir entre si sem contato efetivo através do [[Fluxo magnético]] num fenômeno chamado de [[Indução mútua]] e que tem como principal aplicação os trafos.

Quando temos dois [[Indutores]] próximos, seus fluxos se associam, de modo que se passamos através de um deles uma [[Corrente]], o fluxo magnético que surge nele pode atravessar o outro e gerar uma [[Potencial elétrico|tensão]] induzida.

Levando em conta a [[Lei de Faraday]], sabemos que a tensão no indutor depende da [[Derivada|variação temporal]] do fluxo magnético que passa através dele, desse modo, a tensão no indutor ganha agora um segundo termo, referente a tensão induzida pelo fluxo devido ao acoplamento magnético:

$$
v = L\dfrac{di_1}{dt} \pm M\dfrac{di_2}{dt}
$$

O $M$ nessa relação é a chamada **Indutância Mútua** (capacidade de um indutor induzir tensão em um 
indutor vizinho) dada pela relação:

$$
M_{12} = N_1\frac{d\phi_{21}}{di_2} = M_{21} = N_2\dfrac{d\phi_{12}}{di_1} = M
$$

E medida em Henries.

O sinal $\pm$ na formula é justificado pelo fato da polaridade da tensão induzida no indutor depender da direção da variação do fluxo e portanto da corrente que passa na outra bobina, o que muda a depender de fatores como a posição e geometria dos indutores, para simplificar essa análise, utilizamos a **Convenção do ponto**.

> Se uma corrente entra pelo terminal de uma bobina que está marcado pelo ponto, a polaridade referência da tensão mútua na segunda bobina é positiva no seu terminal marcado pelo ponto

> Se uma corrente sai pelo terminal de uma bobina marcado com um ponto a polaridade é negativa no terminal da outra bobina que está marcado pelo ponto

Um caso especial comum é a conexão de bobinas em série:

![[circ2_001.png]]

Na imagem $(a)$ temos uma conexão em série aditiva, e a indutância do conjunto é $L = L_1 + L_2 + 2M$, na imagem $(b)$ temos uma conexão em série subtrativa, com a indutância do conjunto sendo $L= L_1 + L_2 - 2M$.

Por outro lado, para [[Indutores]] em paralelo, temos uma indutância do conjunto sendo:

$$L = \frac{L_1L_2 - M^2 }{L_1+L_2\mp 2M}$$

Assumimos o sinal $-$ no denominados se a conjugação for aditiva (As duas correntes entrando ou as duas saindo dos pontos) e o sinal $+$ caso contrário.

Um método útil para resolver questões desse tipo envolve o processo representado na seguinte imagem:

![[circ2_002.png]]

Basicamente, ao nos deparar com um conjunto de bobinas acopladas magneticamente, adicionamos em série com cada uma delas uma fonte de tensão alternada, que representará a tensão induzida sobre ela pela corrente na outra bobina, em seguida, determinamos a polaridade dessa fontes utilizando a convenção do ponto identificando se a corrente entra ou sai pelo ponto da outra bobina.