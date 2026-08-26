Assim como utilizamos os [[Números Complexos]] para introduzir os [[Fasores]] e facilitar a nossa análise de redes em regime permanente, podemos introduzir agora uma [[Potência média e instantânea|potência]] complexa, que nos ajudará a realizar cálculos relativos, sobretudo, à correção do [[Fator de Potência]].

Primeiro, definimos os fasores [[Valores Eficazes|eficazes]] de [[Potencial elétrico|tensão]] e [[Corrente]]:

$$\mathbf V_{rms} = \dfrac{\mathbf V}{\sqrt{2}} = V_{rms}e^{j\phi}$$
$$\mathbf I_{rms} = \dfrac{\mathbf I}{\sqrt{2}} = I_{rms}e^{j(\phi-\theta)}$$

De modo que:

$$P = V_{rms}I_{rms}\cos{\theta} = \text{Re}(V_{rms}I_{rms}e^{j\theta}) = \text{Re}(\mathbf V_{rms} \overline{\mathbf I}_{rms})$$

Temos então que o produto $\mathbf V_{rms} \overline{\mathbf I}_{rms}$ é uma potência complexa cuja parte real é a potência média, e a denotamos então por $\mathbf S$:

$$S = \mathbf V_{rms} \overline{\mathbf I}_{rms} = P +jQ$$

Onde $Q$ é denominado [[Potência]] Reativa, cuja unidade é o Var, Volt Ampere Reativo, para distinguir do watt:

$$Q = \text{Im}(\mathbf S) = V_{rms}I_{rms}\sin{\theta}$$

