Vimos que a potência entregue a uma carga em regime permanente CA é uma potência:

$$P = I_{rms}V_{rms}\cos{\theta}$$

Esse produto dos [[Valores Eficazes]] $I_{rms}V_{rms}$ é chamado de Potência Aparente e geralmente é denotado usando as unidade $VA$ ou $kVA$ para evitar confusões com a unidade de potência média, o Watt.

A relação entre potência média e a potência aparente é chamada de fator de potência, um valor adimensional, dado por:

$$fp = \dfrac{P}{V_{rms}I_{rms}} = \cos{\theta}$$

Que bate com o ângulo da impedância da carga. No caso de um ângulo zero, o que equivale a uma impedância puramente resistiva, temos um fator de potência 1. Ajusta esse $fp$ é um assunto muito importante na área de potência.

Como o $fp$ é o mesmo, independente de termos uma carga reativa indutiva ou uma carga reativa capacitiva equivalente, adotamos a convença de caracterizar o $fp$ como atrasado ou adiantado de acordo com a fase da corrente com referência à da tensão, sendo atrasado se tivermos um fator indutivo e adiantado se tivermos um fator capacitivo.

Para corrigir o fator de potência $fp$ de uma [[Impedância|impedância]] $R +jX$ para um fator de potência $FP$ adicionando uma [[Impedância e Admitância|reatância]] $X_1$ em paralelo com ela, $X_1$ deve ser:

$$X_1 = \dfrac{R^2 + X^2 }{R\tan{(\arccos{(FP)})} - X}$$

Onde $\tan{(\arccos{(FP)})}$ é positivo se $FP$ é atrasado e negativo se ele for adiantado.

Para realizar a mesma correção mas adicionando em série um nova impedância $X_2$ usamos:

$$X_2 = R\tan{(\arccos(FP))}-X$$