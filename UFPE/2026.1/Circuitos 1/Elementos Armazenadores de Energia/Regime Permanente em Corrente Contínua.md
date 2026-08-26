Se as únicas fontes independentes de um circuito são fontes de corrente contínua, então após um determinado tempo (Alguns segundos, como veremos), todas as [[Potencial elétrico|tensões]] e [[Corrente|correntes]] se estabilizarão em valores constantes o que se deve ao fato de que essa fontes contínuas exercem sempre influências de estabilização no circuito que predominam na ausência de outras forças.

Quando todas as correntes e tensões alcançam valores constantes dizemos que **o circuito está em regime permanente CC**.

Num regime permanente de corrente contínua, [[Capacitores em circuitos|capacitores]] atuam como circuitos abertos enquanto [[Indutores em Circuitos|indutores]] atuam como curto circuitos de modo que encontrar as tensões e as correntes num circuito nesse regime é um problema simples de fontes constantes, essa análise será essencial também para entender o comportamento inteiro de  um circuito no decorrer do tempo pois através da análise em regime permanente poderemos encontrar as condições iniciais do circuito.

Isso pode ser feito utilizando o fato de que, em um [[Capacitores|capacitor]]:

$$v_C(0^-) = v_C(0^+)$$

E em um [[Indutores|indutor]]:

$$i_L(0^-) = i_L(0^+)$$

Então sabendo que o circuito estava em RP (Regime permanente) analisamos o circuito substituindo os capacitores por circuitos abertos e os indutores por curto circuitos e encontramos as **tensões nesses circuitos abertos** e as **correntes nesses curto circuitos** e, sabendo que essas tensões e correntes são iguais nos capacitores e indutores, respectivamente, no instante imediatamente posterior ao $t_0$ podemos escrever a [[Lei de Kirchhoff das Tensões|LKT]] e a [[Lei de Kirchhoff das Correntes|LKC]] do circuito obtendo [[Equações Diferenciais]] que envolvem as tensões e correntes no circuito.