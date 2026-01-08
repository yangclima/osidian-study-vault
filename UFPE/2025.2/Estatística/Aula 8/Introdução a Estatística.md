Até aqui, lidamos como probabilidade, mas é chegada a hora de finalmente trabalhar com estatística,  a área da ciência que coleta, organiza, analisa e interpreta dados para entender fenômenos e tomar decisões diante da incerteza.

A estatística lida com dados e **seu objetivo é fazer inferência e previsões baseadas nesses dados**, processo que pode ser dividido em $3$ passos simples:

1. Coleta de dados
2. Descrição de dados 
3. Análise de dados

Tudo começa no planejamento do experimento, uma etapa fundamental da coleta de dados que é crucial para garantir que os dados coletados serão úteis, um experimento mal planejado irá gerar dados de péssima qualidade, a partir dos quais pode ser impossível obter inferências úteis e válidas.

> Consultar um estatístico após o término de um experimento é, muitas vezes, como lhe pedir que faça uma autópsia. Ele talvez consiga dizer de quê o experimento morreu.
> 
> - **R.A. Fisher**

O próximo passo, dado que o experimento foi bem e este foi planejado e executado feito é descrever os dados obtidos, o que chamamos de **Estatística descritiva**. Os dados brutos, muitas vezes assumem a forma de um lista, matriz ou banco de dados massivo de rótulos e números, para dar sentido a esses números usamos as **estatísticas resumidas** como a média, mediana e o intervalo interquartil além de podermos visualizar os dados através de **dispositivos gráficos** como os [[Histogramas]], úteis tanto para comunicar quanto para explorar os dados a fim de obter informações a partir da sua estrutura.

Por fim, queremos fazer inferências sobre esses dados, o que frequentemente se dá pela especificação de um **modelo estatístico** para o processo aleatório pelo qual os dados são obtidos, nosso foco é então, tomados os dados e o modelo estatístico, inferir, através desses dados, valores para os parâmetros do nosso modelo.

Apesar de todo o nosso esforço, raramente poderemos fazer afirmações definitivas sobre tais parâmetros, já que os dados por si próprios vem de um processo aleatório, ao invés disso, nossas evidências estatísticas sempre envolverão declarações de probabilidade. Infelizmente a mídia e o público em geral tendem a interpretar mal o significado probabilístico dessas declarações o que leva a constantes confusões, nesse sentido, queremos enfatizar o significado das nossas declarações estatísticas junto com os métodos que as produz.

Ok, entendemos o que é **A Estatística**, mas afinal, o que é **uma estatística**?

Resumidamente, uma estatística é qualquer coisa que possa ser calculada a partir dos dados coletados, por exemplo, digamos que nosso experimento é composto por $600$ lançamentos sucessivos de um dado, nesse caso, algumas estatísticas que podemos definir com relação a esse experimento são: O número de rolagens que obtiveram $6$ como resultado, a média dos resultados das rolagens, ou mesmo coisas como "o quadrado da média das rolagens menos a raiz cúbica da somas dos resultados que obtiveram resultados ímpares", mesmo que isso não seja útil, a probabilidade de se obter um valor $x$ num lançamento, por outro lado, **não é uma estatística**, ela não é um propriedade dos dados e sim do experimento, nesses caso, uma característica do dado e da maneira como o lançamos, porém, podemos **estimar** essa propriedade utilizando os dados coletados, o que poderia ser feito através da proporção das rolagens que obtiveram $x$ como resultado em relação ao total de rolagens.