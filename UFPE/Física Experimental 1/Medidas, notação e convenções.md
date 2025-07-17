Formalmente falando, **uma medição consiste em comparar duas quantidades de uma mesma grandeza**, sendo uma delas definida como um padrão. 

Por sua vez, **o padrão é a convenção que define uma quantidade unitária da grandeza medida** e que por isso recebe um nome especial (e.g. Metro, Quilo, Joule). Essa **comparação entre as grandezas é feita através de um instrumento calibrado pelo padrão de medida** a ser utilizado.

Pela forma como definimos *medição* é evidentemente essencial que toda medida, valor resultante da medição venha acompanhado da unidade de medida padrão, de tal forma que um número desacompanhado da sua respectiva unidade de medida não tem significado físico.

Ao abordar problemas experimentalmente é essencial ter em mente certas limitações relacionadas as nossas medidas no que diz respeito a sua precisão, primeiramente, assumimos que **invariavelmente toda grandeza possui um valor verdadeiro bem definido independente de realizarmos ou não a medição**, apesar disso, as tais imitações relacionadas à medição e à experimentação implicam que jamais seremos capaz de encontrar esse valor verdadeiro, por isso, **não denotamos uma medida através de um valor concreto e sim através de um intervalo no qual temos certeza que esse valor está incluso**, o tamanho desse intervalo é definido pela nossa **incerteza**.

Assim defini-se que **para expressar de maneira coerente o resultado de uma medição, precisamos fornecer o valor mais confiável obtido, sua unidade de medida e a sua incerteza**.

A representação dessa medida pode, portanto, ser feita seguindo o seguinte formato:
$$
m = M \pm \sigma_M
$$
Onde $M$ é o valor mais confiável para a medida, e $\sigma_M$ é a incerteza relacionada a $M$.

# Algarismos significativos
A própria existência da incerteza implica que não faz sentido representar valores com uma quantidade de algarismos significativos incompatível com a confiabilidade relacionada a aquela medida, uma vez que não podemos garantir a correspondência dos valores, dessa forma, nesse curso, adota-se por convenção uma incerteza com apenas um algarismo significativo e o valor mais confiável apresentado deve ser compatível com essa incerteza, utilizando-se caso necessário a notação científica para representar corretamente esse valor.
## Regras de arredondamento
### Regra 1:
Quando o algarismo a ser desprezado for inferior a 5, mantém-se o valor à esquerda inalterado (i.e. arredonda-se para baixo).
### Regra 2:
Quando o algarismo a ser desprezado for superior ou igual a 5, soma-se uma unidade ao valor à esquerda (i.e. arredonda-se para cima).
### Regra 3:
Quando o algarismo a ser desprezado for igual a 5 seguindo de zeros, ainda que implícitos, se o algarismo anterior for ímpar acrescenta-se uma unidade ao seu valor, se for par, permanece inalterado

## Compatibilidade entre medidas
Devido a forma como medimos e apresentamos os resultados de nossas medidas, não faz sentido comparar números bem definidos para compreender a igualdade entre duas medidas, ao invés disso, definimos portando a compatibilidade entre medidas, assim, duas medidas são compatíveis quando seus intervalos de confiança se sobrepõem.
# Incerteza instrumental
Uma das principais fontes de incerteza provém do instrumento de medida que estamos utilizando e é consequência de sua precisão e calibração.

No geral, instrumentos de medida determinam uma quantidade de algarismos significativos de maneira exata (Algarismos significativos) e permitem que o experimentador, por inspeção visual, determine um algarismos adicional, chamado de algarismo inexato, sobre o qual recai a incerteza.

Tomamos por convenção:

- Se o instrumento permitir a avaliação de um algarismo duvidoso, a incerteza instrumental é tomada como a metade da menor divisão de leitura do instrumento.
- Se o instrumento não permitir essa avaliação, a incerteza é tomada como uma unidade do último algarismo da medida.