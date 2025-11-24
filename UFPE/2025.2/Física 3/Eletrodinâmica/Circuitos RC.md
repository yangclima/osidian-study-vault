Como vimos, um [[Circuitos DC|Circuito RC]] formado apenas por [[Corrente e Resistência|resistores]] tem parâmetros constantes no tempo (Corrente e [[Potencial elétrico|diferença de potencial]]), entretanto, uma outra forma comum de construir circuitos inclui [[Capacitores]] que, como vimos, armazenam carga por meio do campo elétrico, dessa forma, incluir capacitores no nosso sistema faz com que os nossos parâmetros passem a variar no tempo já que a carga  no capacitor irá variar e com ela a diferença de potencial ao longo do mesmo. Como esse é um caso comum, damos um nome especial aos circuitos formados pela combinação de resistores e capacitores: Circuitos RC.

Em geral, os circuitos  RC tem a seguinte forma (Se não tiverem, é possível fazer com que tenham usando [[Simplificação de circuitos]]):

![[fg3_013.png]]

O circuito está inicialmente, porém, em $t=0$ fechamos a chave $S$ e permitimos que a corrente circule.

Como vimos, a queda de tensão num capacitor é dada por $\Delta V_C = q/C$, porém, em $t=0$ a carga no capacitor é nula, portanto, não há queda de tensão e temos um circuito puramente resistivo (O capacitor se comporta como um fio), portanto: Em $t=0$, temos (Por [[Leis de Kirchhoff|LKT]]) $\varepsilon - I_0R =0$ o que implica que $I_0 = \varepsilon/R$.

Para um dado instante $t > 0$ a carga no capacitor já não é mais nula e portanto temos um circuito onde vale que $\varepsilon - I(t)R - q(t)/C = 0$, perceba que, como explicitado, a corrente no resistor irá variar no tempo, bem como a carga no capacitor, isso decorre do fato de que quanto mais próximo da sua carga máxima um capacitor está, menos carga consegue passar por ele, assim, como o capacitor está sendo carregado $I(t) = + dq/dt$ e podemos obter a seguinte equação diferencial:

$$
\varepsilon - \dfrac{dq}{dt}R - \dfrac{q}{C} = 0
$$

Essa equação pode ser resolvida por [[Separação de variáveis]] obtendo:

$$
\int_0^q \dfrac{dq}{C\varepsilon - q} = \int_0^t \dfrac{dt}{RC}
$$

Resolvendo essa equação, obtemos a carga no capacitor em função do tempo:

$$
q(t) = C\varepsilon(1 - e^{-t/RC})
$$
Porém, sabemos que a carga máxima no capacitor é $Q_{max} = C\varepsilon$, além disso a constante $RC$ aparece como uma medida do tempo de decaimento dessa exponencial, assim, denominamos $\tau = RC$ como a "Constante de tempo" do circuito, simplificando nossa equação para:

$$
q(t) = Q_{max}(1 - e^{-t/\tau})
$$

A partir da carga do capacitor podemos obter a corrente:

$$
I(t) = \dfrac{dq}{dt} = \left(\dfrac{\varepsilon}{R}\right)e^{-t/\tau} = I_0e^{-t/\tau}
$$

Perceba que, quando $t \rightarrow \infty$ a corrente tende a $0$, ou seja, o capacitor corta o circuito. Por fim, através da carga do capacitor podemos obter a queda de tensão no capacitor como função do tempo:

$$
\Delta V_C(t) = \dfrac{q(c)}{C} = \varepsilon(1 - e^{-t/\tau})
$$

Perceba que, conforme o esperado, quando $t \rightarrow \infty$, $\Delta V_C \rightarrow \varepsilon$, ou seja, se iguala a [[Força eletromotriz|tensão da fonte]], cortando o circuito.

Agora, considerando o capacitor completamente carregado, podemos mudar o nosso referencial temporal tomando $t=0$ o instante em que abrimos novamente a chave $S$, permitindo então que o capacitor descarregue, assim, podemos assumir uma corrente inicial nula e o capacitor passando a agir como um fonte de tensão, assim $I(t) = -dq/dt$ e portanto:

$$
\int_{Q_{max}}^q \dfrac{dq}{q} = -\int_0^t \dfrac{dt}{RC}
$$

Obtemos então:

$$
q(t) = Q_{max}e^{-t/\tau}
$$

Para a corrente, temos:

$$
I = -\dfrac{dq}{dt} = \left(\dfrac{\varepsilon}{R}\right)e^{-t/\tau}
$$

E por fim, para a queda de tensão no capacitor:

$$
\Delta V_C(t) = \dfrac{q(c)}{C} = \varepsilon e^{-t/\tau}
$$