---
prev: "[[Lei de Elemento]]"
next: "[[Terminologia]]"
---
Quando pensamos em circuitos, vem logo a nossa mente a ideia de transferir e fornecer energia para a operação de dispositivos, mas uma das mais amplas utilidades dos circuitos é também a representação e processamento de sinais, essa é a ideia que abre caminho para aplicações como computadores.

A ideia é simples, queremos representar informações através de sinais elétricos, ou seja, como [[Potencial elétrico|tensão]] e [[Corrente]] e então utilizar redes de [[Componentes Ideais|componentes elétricos]] para processar e modificar os sinais convenientemente gerando um resultado agradável.

# Sinais analógicos
A maioria das grandezas do mundo real são analógicas, surgem em intervalos contínuos de valores dessa maneira, a maioria dos circuitos que interage com o mundo real precisa ser capaz de processar esse tipo de sinal.

A principal classe de sinal analógico são os sinais senoidais expressados por uma tensão que segue uma expressão do tipo:

$$
v(t) = A\sin{(\omega t + \phi)}
$$

Onde $A$ é a amplitude do sinal, $\omega$ é a frequência de oscilação do sinal multiplicada por $2\pi$ e $\phi$ é a defasagem do sinal, todos esses parâmetros podem variar e então serem usados para representar informação de algum modo, por exemplo, transmitir informação através da amplitude do sinal.

Sobre esse tipo de sinal, sabemos que a sua média temporal é nula e por isso é essencial a aplicação do conceito de [[Valor Eficaz ou RMS]] quando quisermos falar de média de potência dissipada ou mesmo de amplitude média do sinal.

Algumas representações de sinal são nativas, ou seja, de fato a informação desejada é, naturalmente um sinal elétrico, porém, as aplicações mais interessantes surge quando representamos grandeza que não são naturalmente elétricas como sinais elétricos o que é feito através dos chamados **transdutores**, dispositivos capazes de transformar grandezas físicas não elétricas em sinais elétricos, como as fotoresistores, cuja incidência de luz modifica sua [[Resistência]] e pode então ser usado para transformar a quantidade de luz numa representação elétrica.
# Sinais Digitais
Um outro tipo de sinal são os sinais digitais, base para a abstração dos [[Sistemas Digitais]], a ideia é quantizar a natureza analógica do mundo, enquanto um sinal analógico de tensão assumiria valores contínuos entre um determinado intervalo, os sinais digitais só se interessam em seus limites definidos, por exemplo, se a tensão é maior ou menor que um determinado valor, a grande vantagem é que, dessa maneira, os sinais são menos suscetíveis ao ruído.

Assim como os sinais analógicos, os digitais podem ser usados para representar quantidades não elétricas através dos transdutores ou mesmo elétricas como o fato de uma determinada parte do circuito estar ou não alimentada e pela sua natureza eles são ideais para representar fatos lógicos dando origem [[Sistemas de numeração digital]], em especial o binário.
