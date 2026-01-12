Partindo do princípio da [[Conservação de Energia]], esta definição abstrata só nos é útil se soubermos calcular, isto é, soubermos a fórmula para todos os tipos de energia, assim, podemos chegar na ideia da [[Energia Potencial Gravitacional]] partindo apenas de argumentos teóricos intimamente relacionados com as ideias de conservação de energia de Carnot.

Consideremos inicialmente máquinas de levantar peso, máquinas capazes de levantar pesos abaixando outros pesos, e tomemos como hipótese que não existe movimento perpétuo nessas máquinas, ou seja, é impossível que uma máquina dessas após levantar e abaixar inúmeros pesos e retornar ao seu estado inicial tenha como resultante o levantamento de algum peso, isso, considerando que nenhuma energia entrou no sistema (A máquina não teve nenhuma ajuda externa).

Consideremos entretanto que existem máquinas ideais, denominadas *reversíveis*, que, apesar de se encaixarem na nossa hipótese (Não são máquinas de movimento perpétuo), permitem que seu estado seja revertido, isto é, se usamos 3 pesos para levantar 1, podemos também usar 1 peso para levantar 3.

Consideremos então uma máquina $A$ reversível que, ao abaixar uma unidade de peso por uma unidade de altura, eleva 3 unidades de peso a uma altura $X$. Paralelamente, uma máquina $B$ (não necessariamente reversível) realiza o mesmo processo, elevando as 3 unidades a uma altura $Y$.

Provamos que $Y$ não pode ser maior que $X$. Se fosse, poderíamos usar a máquina $B$ para elevar o peso até $Y$, abaixá-lo até a altura $X$ (obtendo um excedente de energia) e então usar a máquina $A$ de forma reversa para restaurar o sistema ao estado inicial. O resultado seria um saldo positivo de energia sem qualquer fonte externa. Portanto, se o movimento perpétuo é impossível, a máquina reversível representa o limite máximo de eficiência (onde $Y = X$).

A beleza desse resultado está em podermos tomar conclusões de antemão sobre qualquer máquina desse tipo que seja criada, não importa quão complexo seja seu mecanismo e de forma similar, a tristeza é que existe um limite para a eficiência de nossas máquinas. 

Assim, toda e qualquer máquina de levantar pesos criada, não importa seu mecanismo, que abaixe $1$ quilograma ($kg$) por $1$ metro ($m$) e com isso levante três quilogramas, os levantará, sempre a, no máximo, $X$ metros. A pergunta que naturalmente surge agora é então qual seria o valor $X$.

Imagine então o seguinte mecanismo:

![[fey_001.png|center]]

Perceba que entre $a$ e $e$, surge uma equivalência entre elevar três pesos a  uma altura $X$ com elevar um único peso a uma altura $3X$, afinal, a segunda e terceira prateleiras do mecanismo já estavam ocupadas antes, nada mudou, além disso, não é difícil notar que se um peso abaixando uma altura pudesse levantar outro peso idêntico a uma altura maior que a que baixou ou mesmo incapaz de elevar o outro peso a uma altura igual a que abaixou isso violaria ou a nossa hipótese ou a reversibilidade da máquina e poderia permitir o movimento perpétuo, nesse caso, a única possibilidade seria que $3X = 1\ m$ e portanto $X = 1/3 \ m$. 

Tudo isso pode então ser generalizado para o fato de que se $1\ kg$ cai um metro devido ao funcionamento de uma máquina reversível então a máquina pode levantar com isso $p \ kg$ por uma distância de um metro dividido por $p$, dessa maneira, se pegarmos os pesos no estado inicial e multiplicarmos por suas alturas somando os resultados e repetirmos esse processo depois que a máquina funcionar, não haverá mudança, chamamos então a soma dos pesos multiplicados por suas alturas de **energia potencial gravitacional**, a energia que um objeto tem devido sua posição no espaço relativo à Terra.

$$\begin{equation}
\left( 
\begin{array}{c} 
\text{energia potencial} \\ 
\text{gravitacional} \\ 
\text{para um objeto} 
\end{array} 
\right) = (\text{peso}) \times (\text{altura})
\end{equation}$$

De fato, a natureza não precisa se comportar segundo nosso raciocínio, talvez a nossa hipótese inicial pudesse estar errada o que invalidaria nosso argumento, mas nesse caso, para distâncias próximas a terra, foi provado que nosso raciocínio está correto.

Em geral, chamamos de Potencial a energia relacionada a posição relativa de uma coisa em relação a outra, e existe um princípio fundamental que nos diz que:

$$\begin{equation}
\left( 
\begin{array}{c} 
\text{mudança} \\ 
\text{na energia} 
\end{array} 
\right) = (\text{força}) \times
\left( 
\begin{array}{c} 
\text{distância em que} \\ 
\text{a força atua} 
\end{array} 
\right)
\end{equation}$$

O que é muito útil em problemas que envolvem forças e conseguimos dividir em estados iniciais e finais.