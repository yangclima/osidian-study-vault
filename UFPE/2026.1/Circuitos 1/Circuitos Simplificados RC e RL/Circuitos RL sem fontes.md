Num circuito que possui apenas [[Indutores em Circuitos|indutores]] e [[Resistores e Capacitores|resistores]] a única fonte de [[Potencial elétrico|tensão]] e [[Corrente|corrente]] no circuito é a energia armazenada no indutor, que circulará o circuito e será dissipada com o tempo pelo resistor.

Usando [[Lei de Kirchhoff das Tensões]] (Também é possível obter o mesmo resultado usando [[Lei de Kirchhoff das Correntes|LKC]]) podemos obter a seguinte [[Equações Diferenciais|EDO]] para o comportamento do circuito:

$$
iR + L\dfrac{di}{dt} = 0
$$

Que pode ser resolvida por [[Separação de variáveis]] de modo a obter a seguinte equação para a corrente no tempo no circuito:

$$i(t)= I_0e^{-Rt/L}$$

Nesse caso, a [[Constantes de Tempo|constante de tempo]], $\tau$ do nosso circuito é 

$$\tau = \dfrac{L}{R}$$

E a tensão ao longo do indutor será:

$$v(t) = I_0Re^{-Rt/L}$$

