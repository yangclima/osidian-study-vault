Antes de aplicar uma densa abordagem algébrica utilizando as [[Equações de Maxwell]] para entender os fenômenos ópticos envolvendo as [[Maxwell e a previsão das Ondas Eletromagnéticas|ondas eletromagnéticas]] a nível microscópico, podemos observar e elaborar o comportamento dessas entidades físicas a nível macroscópico para tecer conclusões gerais sobre o seu comportamento.

Para realizar nossa abordagem, utilizaremos a chamada **Óptica geométrica**, uma aproximação que assume a trajetória das [[Ondas eletromagnéticas no domínio do tempo|ondas de luz]] como linha retas e que funciona e descreve bem o comportamento delas desde que o tamanho do objeto que está interagindo com a luz seja muito maior que o comprimento de onda da luz visível, isto é, muito maior que $\lambda_{luz} \in [400\, nm, 700\, nm]$. 

Essas linhas retas são os **raios de luz**, que apontam na direção de propagação da onda, sendo, portanto, perpendiculares às frentes de onda, além disso, conjuntos desses raios de luz são chamados de **feixes de luz**.

Quando incidimos um feixe de luz em um meio material, podemos visualizar dois fenômenos que surgem da interação desse feixe com a interface entre os meios, por vezes, ao mesmo tempo, a **Reflexão** (parte do feixe é rebatido para o meio de origem) e a **Refração** (Parte do feixe segue uma trajetória para dentro do meio no qual o feixe está incidindo).

Temos então 3 ângulos muito importantes nesse contexto, o **ângulo de incidência**, o **ângulo de reflexão** e o **ângulo de refração**, todos medidos com relação a uma reta normal à superfície sob a qual o feixe está incidindo:

![[fg4_001.png]]

Fato importante é que os raios incidente, refletido e refratado estão num mesmo plano, denominado **plano de incidência**, ortogonal à interface do meio e a cada meio $i$ atribuímos um **índice de refração**, $n_i \geq 1$ onde $n_i = c/v_i$ e $v_i$ representa a velocidade da luz no meio. 

A primeira constatação é sobre o fenômeno da reflexão, normalmente denominada, **Lei da reflexão**, e diz:

> O ângulo de incidência $\theta_1$ é igual ao ângulo de reflexão $\theta^\prime_1$. 
> $$\theta_1 = \theta_1^\prime$$

A segunda observação refere-se ao fenômeno da refração e chama-se de **Lei de Snell**, que diz:

> O ângulo de refração $\theta_2$ se relaciona com os índices de refração dos meios $n_1$ e $n_2$ e com o ângulo de incidência $\theta_1$ pela relação: 
> $$n_1\sin{\theta_1}=n_2\sin{\theta_2}$$

Quanto a frequência e comprimento de onda ao atravessar um meio material, temos o seguinte:

> Quando uma onda passa de um meio $1$ para um meio $2$, seu comprimento de onda $\lambda$ se altera, porém, sua frequência $f$ (E, portanto, $\omega$) permanece inalterada. O comprimento de onda se altera segundo a relação dada por $n = \lambda_{vácuo}/\lambda$.

Essa última observação está intimamente relacionada a uma fenômeno notável e muito famoso, a **Dispersão cromática**, um raio de [[Polarização de ondas eletromagnéticas|luz natural]] possui diferentes onda sobrepostas com diferentes comprimentos de onda e como essa característica está relacionada ao índice de refração por $n = \lambda_{vácuo}/\lambda$ diferentes comprimentos de onda (Diferentes cores), tem diferentes ângulos de refração o que faz com que, de forma mais acentuada em alguns materiais, a onda seja separada em componentes que vão do violeta (Menor ângulo de refração) ao vermelho (maior ângulo de refração).

Um outro interessante fenômeno é a chamada **Reflexão total**, que ocorre quando a luz tenta passar de um meio com um índice de refração maior para um meio com índice de refração menor, basicamente, existe um ângulo crítico $\theta_c$ para o qual qualquer raio com ângulo de incidência $\theta_1$ maior que $\theta_c$ permanece dentro do meio atual, como caso especial temos $\theta_1 = \theta_c$, para o qual o raio refletido segue uma trajetória rente a interface entre os meios, ou seja, $\theta_1^\prime = 90\degree$, esse ângulo crítico é dado por $\sin{\theta_c} = n_2/n_1$.

Um último fenômeno notável envolvendo a luz é o fato de que através da incidência de um raio de luz em um meio, podemos [[Polarizadores|polarizar]] a onda eletromagnética fazendo com que todas as direções de polarização sejam enviadas no raio refratado e apenas uma, cuja polarização é paralela a interface entre os meios, isso ocorre quando o ângulo de incidência tem um valor especial $\theta_B$, chamado de **ângulo de Brewster**, dado segundo a expressão $\tan{\theta_B} = n_2/n_1$, importante ter em mente que nesse caso específico o ângulo entre o raio refletido e refratado é exatamente $90\degree$.


