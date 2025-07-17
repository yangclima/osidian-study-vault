# Propagação de incertezas por composição triangular
Muitas vezes não é possível [[Medidas, notação e convenções|medir]] diretamente a grandeza na qual estamos interessado, mas podemos obtê-la por meio de uma relação entre mais de uma medida, nesse caso precisamos usar a **Propagação de incertezas** para avaliar como as incertezas individuais de cada medida afetam o valor final obtido para a nossa grandeza de interesse.

Uma forma de calcular essa propagação é sermos conservadores e considerarmos um intervalo que garanta que mesmo que o valor real de cada grandeza medida esteja no limite do intervalo definido pela sua respectiva incerteza, o valor resultante da relação esteja incluso no intervalo definido pela grandeza propagada.

O grande problema desse método de propagação de incerteza é que ele é muito pessimista, a probabilidade dos valores reais estarem todos em seus limites superiores de incerteza é muito baixa, assim é mais plausível determinar a incerteza levando em consideração essas probabilidades, assim, **para valores obtidos a partir da soma de medidas bem como para a composição de fontes de incerteza independentes, devemos usar uma regra de composição triangular**:
Se uma medida $M$ é dada por:
$$
M = m_1 + m_2 + \cdots + m_k
$$
Sua incerteza $\sigma_M$ é dada por:
$$
\sigma_M = \sqrt{\sigma_{m_1}^2 + \sigma_{m_1}^2 + \cdots + \sigma_{m_k}^2}
$$
E enunciamos portanto a medida da seguinte forma:
$$
M \pm \sqrt{\sigma_{m_1} + \sigma_{m_1} + \cdots + \sigma_{m_k}}
$$
Da mesma forma, se uma medida $M$ está submetida a $n$ fontes de incerteza independentes $\sigma_1, \sigma_2, \cdots, \sigma_n$ a incerteza total é:
$$
\sigma_M = \sqrt{\sigma_1^2 + \sigma_2^2 + \cdots + \sigma_n^2}
$$
# Propagação de incertezas por linearização e derivadas parciais
Quando a grandeza na qual estamos interessados é dada por relações mais complexas que a soma precisamos de uma outra maneira de avaliar a nossa incerteza, essa maneira de avaliação parte da análise de como o valor obtido para nossa grandeza muda de acordo com a variação de cada uma das medidas das quais depende, assim,  a pergunta que queremos responder é: Qual a relação matemática que relaciona a variação possível da nossa medida dentro do seu intervalo de incerteza com o valor obtido para a nossa grandeza de interesse?

Para uma relação dada por uma única variável, a resposta é a derivada da função \