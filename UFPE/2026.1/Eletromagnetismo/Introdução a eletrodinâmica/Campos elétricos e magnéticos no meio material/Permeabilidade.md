A permeabilidade magnética $\mu$ é a grandeza física que caracteriza como a matéria responde a presença de um campo magnético e é expressa em *Henries por Metro* $[H\cdot m^{-1}]$.

A permeabilidade magnética do vácuo é $\mu_0 = 4\pi\times10^{-7} \ H \cdot m^{-1}$, onde $\vec B = \mu_0 \vec H$, a permeabilidade da matéria inclui as contribuições para o campo $\vec B$ provenientes dos momentos de dipolo magnético atômicos alinhando-se com o campo $\vec H$ aplicado. Esses momentos de dipolo surgem de elétrons orbitando os núcleos atômicos ou de partículas carregadas em rotação onde essa carga em movimento é a corrente.

Todos os elétrons tem Spin $\pm 1/2$ além de qualquer Spin orbital em torno do núcleo e o Spin resultante de um átomo pode ser não nulo e seus campos magnéticos estão conectados com suas correntes equivalente pela [[Lei de Ampére]]: $\nabla \times \vec H = \vec J + \frac{\partial \vec D}{\partial t}$.

Em qualquer meio, a contribuição acumulada dos dos momentos de dipolo magnéticos atômicos induzidos para $\vec B$ é caracterizada por um vetor magnetização $\vec M$ definido como:

$$
\vec B = \mu\vec H =  \mu_0(\vec H + \vec M) = \mu_0\vec H(1+ \chi_m)
$$

Onde $\chi_m$ é a susceptibilidade magnética do meio, usada para classificar os materiais em **Diamagnéticos**, onde efeitos quânticos fazem com que $\chi_m$ seja negativo e portanto $\mu < \mu_0$, **Paramagnéticos**, onde $\chi_m$ é ligeiramente positivo, e os **Ferromagnéticos**, onde $\chi_m$ assume valores altíssimos.

A diferença gigantesca entre materiais normais onde $\mu \approx \mu_0$ e os materiais ferromagnéticos onde $\mu >> \mu_0$ deve-se ao alinhamento espontâneo dos momentos de dipolo magnético atômicos na mesma direção de modo que ao aumentar o campo magnético, os dipolos restantes se reorientam, ou seja, se a susceptibilidade magnética de um material é superior a um certo limite, então os dipolos atômicos se alinham em regiões chamadas de domínios magnéticos cujo tamanho é limitada pela estrutura granular do material ou por considerações energéticas, tendo tamanhos típicos da ordem de micrômetros para minimizar a energia armazenada ($\mu \vec H^2$), caso a estrutura do material não seja um fato limitante, os domínios tendem a crescer a medida que o campo magnético externo $\vec H$, aumenta.

Como os limites dos domínios não transpõem facilmente os limites da estrutura granular do material, podemos projetar essa estrutura do material para controlar propriedades magnéticas, de forma que se as paredes dos limites se movem facilmente, $\chi_m$ é grande.

Sob o efeito de campos magnéticos suficientemente fortes, todos os domínios magnéticos se expandem ao seu tamanho máximo e/ou rotacionarão na direção do campo $\vec H$, chegando ao estado de **Saturação Magnética** e ao valor máximo do vetor $\vec M$. Esse comportamento é que resulta no comportamento típico não linear da curva de magnetização de um material, a inclinação da curva é $\mu$ próximo a origem e $\mu_0$ próximo a saturação.

![[elmg_001.png|center|500]]

Se os domínios resistirem a mudança do campo magnético e dissiparem energia nesse processo, temos o surgimento da chamada curva de Histerese, um perfil típico da curva B vs. H, a qual podemos demonstrar que a área corresponde a energia dissipada por ciclo de magnetização a medida que $\vec H$ oscila:

![[elmg_002.png|center|500]]

Materiais magnéticos denominados "Duros" possuem um alto **Fluxo magnético residual** $B_r$ e  alta **Força Coerciva Magnética**, ou **Coercividade** $H_c$ de tal forma que $B_r$ corresponde ao campo magnético residual no material quando nenhum campo magnético externo está sendo aplicado e $H_c$ corresponde ao campo externo $\vec H$ que precisamos aplicar para desmagnetizar esse material, isto é, levar $\vec B$ a zero.

Como $\vec H = 0$, em imãs permanentes a densidade de energia magnética é $W_m = {\vec H}/2 \cdot \vec B =0$ dentro desses imãs e $W_m = \mu{\vec H^2}/2$ $[J\cdot m^{-3}]$ fora deles.

Por fim, representando por $\vec m$ o momento de dipolo magnético de um átomo onde para um laço de corrente de intensidade $I$ e área $\hat n A$, $\vec m = \hat n I A$ $[A\cdot m^2]$, pode ser demonstrado que $\vec M = n\cdot \vec m$ onde $n$ $[m^{-3}]$ é a densidade numérica de dipolos atômicos por metro cúbico, usando uma aproximação semelhante a usada para demonstrar a origem do vetor [[Permissividade|Polarização]].