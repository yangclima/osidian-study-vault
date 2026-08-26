O primeiro circuito que analisaremos na presença de [[Capacitores em circuitos|capacitores]], é  circuito formado apenas por [[Resistores e Capacitores]] sem a presença de [[Componentes Ideais#Fontes Ideais de Tensão e Corrente|fontes]], nesses circuitos, iniciamos com alguma energia armazenada nos [[Capacitores]] que será dissipada ao longo do tempo nos resistores, de modo que a resposta do circuito nesse caso é chamada de **Resposta Natural** já que não envolve forças externas (Fontes) aplicadas no circuito.

O método básico de solução nesse caso é aplicar [[Lei de Kirchhoff das Tensões|LKT]] e/ou [[Lei de Kirchhoff das Correntes|LKC]] ao circuito  considerando a corrente ao longo do capacitor como sendo 

$$i(t) = C\dfrac{dv}{dt}$$

E obtendo assim uma [[Equações Diferenciais|EDO]] em $v$ do funcionamento do circuito que pode ser resolvida por [[Separação de variáveis]] e que nos dará a tensão no circuito como função do tempo e deve ser resolvida levando em conta as condições iniciais do circuito.

Para o circuito $RC$ padrão iremos obter:

$$\dfrac{v}{R} + C\dfrac{dv}{dt} = 0$$

Que resolvida nos retorna:


$$
v(t) = V_0e^{-t/RC}
$$

E de forma similar:

$$i(t) = \dfrac{V_0}{R}e^{-t/RC}$$

