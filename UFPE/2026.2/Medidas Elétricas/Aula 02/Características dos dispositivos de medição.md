Algumas características são muito importantes para detalhar tanto o [[Dispositivos de medição]] quanto as [[Metrologia|medidas]] feitas com ele, por isso, analisaremos algumas dessas características e especificações:

> **Intervalo (ou faixa) de indicação (Também chamado de range ou escala):** Conjunto de valores limitados pelas indicações extremas. O intervalo de indicações é o intervalo entre o menor e maior valor que o dispositivo mostrador do SM teria condições de apresentar como indicação direta.

Para um equipamento digital o intervalo de indicações é melhor expresso pelo número de dígitos que podem ser mostrados, apesar disso, em alguns casos so de olhar o número de dígitos que um mostrador digital tem não conseguiremos dizer com certeza quantos valores ele pode expressar, isso por que em alguns casos esses equipamentos tem um **meio dígito**, um dígito que só exibe zero ou um, então, se dizemos que um equipamento tem $3$ dígitos e $1/2$  ele então tem um range de $\pm 1999$.

Além disso, alguns dispositivos tem vários intervalos de indicação, como os multímetros que nos permitem selecionar um intervalos desses para obter uma medida mais precisa, cada um desses intervalos é chamado de **Intervalo (ou faixa) nominal de indicação**. E nesse contexto temos:

> **Amplitude (Span):** Diferença em módulo entre os dois limites de um intervalo nominal de indicação.

A capacidade de exibir entretanto não garante que o instrumento é capaz de medir com presteza um determinado valor, por isso, definimos:

> **Intervalo de medição** Valores que podem ser medidos por um dado instrumento ou sistema de medição com erro de medição especificado pelo fabricante, sob condições determinadas.
 
Ainda assim, existe uma lacuna: que variações da grandeza são ou não percebidas pelo meu equipamento de medição e nesse contexto, definimos:

> **Resolução:** Menor variação da grandeza que está sendo medida, que causa uma variação perceptível na indicação correspondente

Essa resolução é igual ao **incremento digital** nos sistemas digitais, teoricamente zero no sistemas com mostrador analógico e é chamado de **divisão de escala** em sistemas analógicos como réguas.

Além disso, para medir não só a capacidade de "reagir" a mudanças no mensurando introduzimos a sensibilidade como relação entre a quantidade que a resposta altera-se para uma dada alteração do mensurando:

> **Sensibilidade (S):** É a razão da variação na saída (ou resposta ou indicação) pela variação da entrada (ou estímulo ou grandeza medida). Geometricamente, a sensibilidade corresponde à inclinação da curva característica de resposta. A sensibilidade é constante se a curva de resposta for linear. Caso contrário, será uma determinada função e a sensibilidade é sua derivada.

Note que enquanto a resolução está geralmente associada a limitações do hardware, como o número de dígitos do mostrador, a sensibilidade está relacionada a própria natureza do fenômeno avaliado e ao sensor ou transdutor utilizado.

Temos ainda:

> **Fundo de escala:** Máximo valor que pode ser mensurado por um instrumento

>**Zona morta:** Faixa à qual a entrada varia sem dar início a mudança observável na saída. Geralmente expressa percentualmente com relação ao fundo de escala e pode ser gerada por, por exemplo, folgas em peças móveis.

> **Histerese:** Propriedade de um elemento sensor evidenciada pela dependência do valor de saída na história de excursões anteriores para uma dada excursão de entrada.

Basicamente está relacionada a um espécie de valor residual das medições anteriores, lembra as curvas de [[Magnetização em Materiais]] em materiais ferromagnéticos e está associada a uma curva de retorno diferente da curva inicial de detecção.

Quanto a exatidão do instrumento, temos:

> **Classe de exatidão do instrumento de medição:** É a indicação do máximo erro, especificado pelo fabricante, que pode ser obtido dentro da faixa de indicação. Normalmente é dada percentualmente  em relação ao fundo de escala

> **Deriva Instrumental (Drift):** Mudança indesejável que ocorre no sinal medido com o passar do tempo, causada por fatores ambientais ou por fatores intrínsecos ao sistema, geralmente faz com que o zero da medida seja deslocado.

Para ter segurança no uso dos instrumentos de medidas elétricas você deverá escolher aquele que tem as características necessárias à medição a ser feita e essas características são expostas e representadas através de um conjunto de símbolos específicos:

![[UFPE/2026.2/Medidas Elétricas/imagens/me_001.png]]

![[UFPE/2026.2/Medidas Elétricas/imagens/me_002.png]]

![[UFPE/2026.2/Medidas Elétricas/imagens/me_003.png]]

![[UFPE/2026.2/Medidas Elétricas/imagens/me_004.png]]

Quando a simbologia, em vários manuais de uso usa-se para quantificar a precisão do equipamento o $D$ que se refere à resolução, por exemplo, $\pm (0.5\% + 5D)$ se refere a $0.5\%$ do fundo de escala mais 5 vezes a resolução n dado intervalo nominal de medição.

Os equipamentos também são classificados em categorias de acordo com a segurança e condições de uso, quanto maior a categoria, mais resistente o equipamento é contra um possível transiente na rede.

![[UFPE/2026.2/Medidas Elétricas/imagens/me_005.png]]

