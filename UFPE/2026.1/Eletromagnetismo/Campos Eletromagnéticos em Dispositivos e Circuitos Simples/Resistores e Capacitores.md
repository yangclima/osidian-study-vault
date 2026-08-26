Uma importante aplicação da análise dos [[Campo Elétrico|campos elétricos]] e [[Campo Magnético|magnéticos]] é em simples dispositivos eletrônicos como resistores, capacitores e indutores, os quais, em geral, em altas frequência apresentam mutuamente características um dos outros.

Estes dispositivos podem ser analisados em termos de seus comportamentos:

1. **Estáticos**: Quando podemos tomar $\partial d/\partial dt = 0$ nas [[Equações de Maxwell no domínio do tempo|equações de Maxwell]]
2. **Quase-estáticos**: Quando não podemos tomar $\partial d/\partial dt = 0$ mas podemos assumir $\partial d^2/\partial dt^2 = 0$ nas [[Equações de Maxwell]]
3. **Dinâmicos**: quando não podemos assumir nem que a primeira nem que a segunda derivada temporal é negativa nas equações de Maxwell

Analisaremos casos e geometrias simples desses dispositivos que serão fáceis de entender e nos permitirão, em breve, estender o conhecimento para dispositivos mais complexos.

Estabelecemos acima que estes dispositivos apresentam uns as características dos outros em alta frequência, isso se deve a simples natureza dos materiais e das grandezas eletromagnéticas: Todo condutor apresenta alguma resistência, toda [[Corrente]] gera campos magnéticos e portanto contribui para a [[Indutores|indutância]] e toda diferença de [[Potencial elétrico]] gera campos elétricos e portanto contribui para a [[Capacitores|capacitância]], apesar disso, cada dispositivo, isto é, Capacitor (C), indutor (L) e resistor (R) é desenvolvido e projetado para apresentar apenas uma característica dominante em baixas frequências.

# Resistores
[[Resistores Lineares|Resistores]] são dispositivos de dois terminais caracterizados pela sua [[Resistência]] $R$ $[Ohms: \ohm]$:

$$v(t) = Ri(t)$$

Onde $v(t)$ é a tensão entre os seus terminais e $i(t)$ a corrente através do dispositivo, de tal modo que uma diferença de potencial de $1 \ V$ através de um resistor de $1 \ \ohm$ faz surgir nesse resistor uma corrente de $1 \ A$ e é assim que se define o *Ohm*.

Um exemplo básico de resistor é visto na imagem a seguir:

![[elmg_003.png|center]]

Trata-se de duas placas perfeitamente condutoras entre as quais é colocado um meio de [[Permissividade]] $\varepsilon$, [[Condutividade]] $\sigma$, [[Permeabilidade]] $\mu$, e espessura $d$, possuindo então uma área de seção transversal $A$ constante e paralela ao plano $x-y$. Assumimos então que há uma diferença de potencial $v$ entre as placas e que uma corrente $i$ flui através desse resistor. Assim, algumas restrições serão impostas a esse dispositivo pelas equações que conhecemos até agora:

1. As [[Condições de contorno para campos eletromagnéticos|condições de contorno]], mais especificamente $\vec E \times \hat n = 0$ implica que o campo elétrico no resistor será perfeitamente perpendicular as placas.
2. A [[Lei de Faraday]] implica que qualquer [[Integrais de linha|integral de linha]] através de qualquer caminho entre as duas placas seja igual a diferença de potencial entre elas, isto é, $v$
3. A simetria do capacitor e uniformidade da condutividade $\sigma$ do meio implicam que o campo elétrico será na direção $\hat z$ e terá uma magnitude uniforme $E_0$
4. Na há acúmulo de [[Carga]] no resistor visto que o campo elétrico não é [[Divergente]].

Assim, teremos:

$$\int_0^d\vec E \cdot \hat z\, dz = v = E_0d \implies E_0 = v/d \implies \vec E = \dfrac{v}{d}\hat z$$

Um campo elétrico que induzirá uma densidade de corrente elétrica no meio dada por:

$$\vec J = \sigma\vec E = \dfrac{\sigma v}{d}\hat z$$

De modo que a corrente total é essa densidade integrada sobre a área condutora:

$$\iint_A \vec  J \cdot \vec z\, dA = \iint_A \dfrac{\sigma v}{d}\hat z \cdot \vec z\, dA = i \implies i = \dfrac{\sigma v A}{d}$$

Mas como $i = v/R$:

$$R = \dfrac{d}{\sigma A}$$

E a potência dissipada nesse dispositivo é a sua densidade potência $p_d = \vec E \cdot \vec J$, medida em Joules por metro cúbico $[J\cdot m^{-3}]$ integrada sobre seu volume, isto é:

$$P = \iiint_V \vec E \cdot \vec J dV = \iiint_V \sigma E^2dV = \iiint_V \dfrac{\sigma v^2}{d^2}dV = \dfrac{\sigma v^2V}{d^2}$$


Mas $V = A\cdot d$:

$$P = \dfrac{\sigma A v^2}{d} \implies P = \dfrac{v^2}{R} = Ri^2$$

Assim, acabamos de deduzir o comportamento do resistor e a **Lei de Ohm**.

Ainda aqui, de fácil compreensão, sabemos que $\hat n \cdot \vec D = \rho_s$ o que implica que, no nosso resistor, na placa positiva, teremos uma densidade superficial de carga dada por $\rho_s = \varepsilon E_0$, e portanto uma carga total $\varepsilon E_0 A$, o que nos dá que vale a relação $Q = \varepsilon E_0 A = Cv$ e portanto, há uma capacitância $C = \dfrac{\varepsilon E_0 A}{d}$ no nosso dispositivo.

# Capacitores
Capacitores são dispositivos lineares de dois terminais que armazenam uma carga $Q$ e são caracterizados por sua capacitância $C$, dada em *Farads*, satisfazendo a relação:

$$Q = Cv$$

Onde $v$ representa a tensão entre os terminais do capacitor. 

A estrutura que vimos para o resistor é semelhante a estrutura básica para o capacitor, com a importante diferença de que aqui, temos, em geral, um meio entre as placas com [[Condutividade]] nula $\sigma = 0$. Nesse caso, em baixas frequências essa estrutura se verte em uma capacitor puro.

Apesar de alguns capacitores serem preenchidos com ar, onde a [[Permissividade]] é $\varepsilon \approx \varepsilon_0$, normalmente materiais com maiores permissividades são aplicados, de modo que, os valores típicos das constantes dielétricas desses materiais costumam estar entre 1 e  1000.

Em todo caso, as [[Condições de contorno para campos eletromagnéticos]] requerem um [[Campo Elétrico]] perfeitamente perpendicular as placas condutoras e a [[Lei de Faraday]] requer que a [[Integrais de linha|integral de linha]] por qualquer [[Parametrização de curvas|caminho]] entre as placas tenha o mesmo valor, $v$, condições estas satisfeitas por um campo elétrico $\vec E = E_0\hat z$ entre as placas.

O espraiamento, distorção do campo elétrico na parte externa do capacitor, também conhecido como efeito de borda pode ser negligenciado desde que o espaço $d$ entre as placas seja pequeno quando comparado com seu diâmetro, uma configuração comum nesse tipo de dispositivo.

Temos então que $E_0 = v/d$ e que sua densidade superficial de [[Carga]] na placa positiva, é dada por $\rho_s = \varepsilon E_0 = \varepsilon v/d$ e portanto a carga total nessa placa é:

$$Q = \dfrac{A\varepsilon v}{d} = Cv$$

De tal modo que, nesse tipo de capacitor (Placas paralelas):

$$C = \dfrac{A\varepsilon}{d}$$

Além disso, usando os princípios da conservação de carga, podemos escrever a [[Potencial elétrico|tensão]] entre os terminais do capacitor como função do tempo como:

$$v(t) = \dfrac{Q(t)}{C} = \dfrac{1}{C}\int_{-\infty}^ti(t)dt$$

E de modo similar:

$$i(t) = C\dfrac{dv(t)}{dt}$$

Quanto a equivalência de capacitores, pode se provar através de suas propriedades, que ao ligá-los em série temos:

$$C_{eq}^{-1} = C_1^{-1} + C_2^{-1}$$

E ao ligá-los em paralelo:

$$C_{eq} = C_1 + C_2$$

Quanto a energia armazenada nesse tipo de dispositivo, temos que, a densidade instantânea de energia elétrica armazenada em um capacitor é $w_e$, medida em *Joules por metro cúbico* $[J\cdot m^{-3}]$ e é dada pelo Teorema de Poynting por:

$$w_e = \dfrac{\varepsilon E_0^2}{2}$$

E sua energia total armazenada é então:

$$W_e = \iiint_V w_edv = \dfrac{Cv^2}{2}$$

