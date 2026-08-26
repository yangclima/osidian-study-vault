Um erro comum ao medir grandezas elétricas é o chamado **Erro por efeito de carga**, basicamente, ao utilizar um amperímetro ou um voltímetro, estamos conectando uma carga no circuito para efetuar a medição, com isso, adicionamos uma [[Resistência]], em série (no caso do amperímetro) ou em paralelo (no caso do voltímetro) nesse caso, modificamos os parâmetros elétricos do sistema, mesmo que de maneira quase desprezível na maioria dos casos:

No caso do amperímetro teremos:

$$I_A = \frac{V_0}{R_0 + R_A} \implies \frac{I_A}{I_0} = \frac{R_0}{R_0 + R_A} < 1$$

Onde $I_A$ é a [[Corrente|corrente]] no amperímetro, $R_A$ a resistência do amperímetro e os valores com o subscrito $0$ são o parâmetro originais, nesse caso, temos o erro:

$$\varepsilon= \frac{I_A - I_0}{I_0} = \frac{I_A}{I_0}-1 =  \frac{R_0}{R_0 + R_A} - 1= - \frac{R_A}{R_0 + R_A}$$

Desse modo, visualizamos que para diminuir $\varepsilon$ precisamos diminuir $R_A$ e quando $R_A \to 0$, $\varepsilon \to 0$.

No caso do voltímetro, tomando $V_V$ como a [[Potencial elétrico|tensão]] no voltímetro:

$$V_V =  \frac{R_V}{R_V + R_0}V_0$$

E teremos um erro:

$$\varepsilon = \frac{V_V - V_0}{V_0}= \frac{V_V}{V_0}-1=-\frac{R_0}{R_0+R_V}$$ 
De modo que quando aumentamos $R_V$, diminuímos o erro e quando $R_V \to \infty$, $\varepsilon \to 0$.

