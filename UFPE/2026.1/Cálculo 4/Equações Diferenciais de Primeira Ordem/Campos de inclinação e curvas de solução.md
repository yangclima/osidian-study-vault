A maioria das [[Equações Diferenciais]] não podem ser resolvidas de maneira analítica, ou seja, algebricamente, por isso, vamos desenvolver uma série de métodos numéricos e gráficos que permitem inferir, ao menos de forma aproximada, soluções para essas equações, dentre estes métodos, o primeiro  deles é a inferência de **curvas de solução através de campos de inclinação**.

Para entender esse método, imagine uma equação diferencial como essas a seguir:

$$
\dfrac{dy}{dx} = f(x,y)
$$

Como sabemos, a derivada de uma função pode ser interpretada como com a inclinação da [[O problema da reta tangente|reta tangente]] a curva função num determinado ponto dessa curva, dessa maneira, podemos imaginar que encontrar a solução para uma EDO de primeira ordem seja, nada mais que encontrar uma função cuja inclinação da reta tangente em cada ponto de sua curva seja dada por $f(x,y)$, o exemplo mais simples seria uma equação do tipo:

$$
\dfrac{dy}{dx} = A
$$

Aqui, procuramos uma função cuja inclinação da reta tangente a sua curva seja constante e igual a $A$, o que intuitivamente sabemos que é uma reta de coeficiente angular $A$, assim, é de se esperar que a solução geral para essa equação seja $y(x) = Ax + C$ o que, de fato é verdade.

Esse exemplo foi simples, mas esse princípio vale para qualquer tipo de equação diferencial de primeira ordem na forma normal, assim, para resolver os casos mais complexos, construímos os chamados **campos de inclinação** a ideia é desenhar para cada ponto $(a,b)$ pequenos segmentos de reta que tenham inclinação $f(a,b)$, por exemplo, o seguinte campo de inclinações (Também chamado de campo de direções) é referente a equação diferencial 
$\dfrac{dy}{dx} = -\dfrac{x}{y}$. Feito o campo de direção da função, queremos então encontrar o perfil geométrico da função que é solução dessa equação diferencial, nesse caso, percebemos que deve ser algo como $x^2 + y^2 = C$ já que esta função acompanha a inclinação do campo de inclinação da função e de fato, essa é uma solução para a equação e a chamamos então de **curva de solução**.

![[c4_001.png|center]]


A construção desses campos pode ser feita tanto computacionalmente quanto manualmente, porém, manualmente, é mais simples que este campo seja construído através da construção de isoclines, ou seja, traçando no plano os locus geométricos para os quais a inclinação da função deve ser a mesma. 

A ideia é que depois de traçar os isoclines criando então o campo de inclinações possamos traçar as curvas integrais ou curvas de solução da equação diferencial encontrando então soluções para ela.