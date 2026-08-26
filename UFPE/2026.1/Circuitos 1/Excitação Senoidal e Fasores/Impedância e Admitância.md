Dado um circuito qualquer visto pelos seus terminais, utilizando os [[Fasores]], podemos definir a resistência que um circuito oferece a passagem de corrente como um [[Números Complexos|número complexo]] denominado **Impedância** e definido como:

$$Z = \frac{\mathbf{V}}{\mathbf{I}} = \dfrac{V_m}{I_m}\angle(\phi_V -\phi_I)$$

É importante notar, no entanto, que $Z$ não é um fasor.

Na forma retangular temos então:

$$Z = R + jX$$

Onde $R$ é a componente resistiva da [[Impedância|impedância]] e $X$ é a sua componente reativa. De modo que:

$$|Z| = \dfrac{V_m}{I_m} = \sqrt{R^2+ X^2} $$

Assim, para os [[Resistores Lineares|resistores]] temos:

$$Z_R = R$$

Para os [[Indutores em Circuitos|indutores]]:

$$Z_L = j\omega L = \omega L \angle 90\degree$$

Para os [[Capacitores em circuitos|capacitores]]:

$$Z_C = -\dfrac{j}{\omega C} = \dfrac{1}{\omega C}\angle -90\degree = -\dfrac{1}{\omega C}\angle 90\degree$$

Dizemos então que a impedância de um resistor é puramente resistiva enquanto a impedância dos indutores e capacitores é puramente reativa:

$$X_L = \omega L \implies Z_L = jX_L$$
$$X_C = -\dfrac{1}{\omega C} \implies Z_C = jX_C$$

Desse modo, se a parte reativa da impedância de um circuito é positiva dizemos que ela é indutiva, enquanto que, se ela for negativa, dizemos que se trata de uma impedância capacitiva.

Podemos ainda pensar no inverso da impedância:

$$Y = \frac{1}{Z}$$

Onde temos:

$$Y = G + jB $$

Onde $G$ é denominada [[Condutância|condutância]] e $B$ é denominada susceptância e se relacionam com a impedância por:

$$Y = \dfrac{1}{Z} = \dfrac{1}{R + jX}$$

De forma que:

$$G = \dfrac{R}{R^2 + X^2}$$
$$B = -\dfrac{X}{R^2 + X^2}$$

De forma que aqui, $R$ e $G$ não são recíprocos, exceto no caso puramente resistivo.


