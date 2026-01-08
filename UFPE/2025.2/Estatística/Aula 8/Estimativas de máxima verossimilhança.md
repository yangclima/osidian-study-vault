Até agora, nosso foco foi calcular com base num modelo paramétrico com parâmetros conhecidos, no caso um modelo de distribuição ([[Distribuição Normal]], [[Distribuição Binomial|binomial]], [[Distribuição Geométrica|geométrica]], [[Distribuição de Pareto|de Pareto]], [[Distribuição Exponencial|exponencial]], [[Distribuição de Bernoulli|de Bernoulli]], [[Distribuição Hipergeométrica|hipergeométrica]], [[Distribuição Uniforme Contínua|uniforme contínua]] e [[Distribuição Uniforme discreta|discreta]], entre outras) a probabilidade da obtenção de um determinado resultado.

A partir de agora, nós inverteremos completamente esse jogo, já que a **estatística inferencial busca estimar a probabilidade dos parâmetros de um modelo estatístico a partir dos dados coletados**.

O primeiro método que conheceremos e que permite estimar esses parâmetros, são as **Estimativas de Máxima Verossimilhança** (EMV), a ideia é basicamente responder a seguinte pergunta:

> Assumindo que os dados seguem um determinado modelo paramétrico, para que valor dos parâmetros os dados observados tem a maior probabilidade?

A  grande vantagem desses método é que ele é fácil de aplicar e seu funcionamento corresponde a nossa intuição. A ideia, explicando de maneira simples, é que a partir de um conjunto de dados coletados, digamos os dados obtidos a partir de $100$ lançamentos de um dados, consideremos a estatística que corresponde ao número de lançamentos que resultaram no valor $6$, digamos, $19$, assumindo que a obtenção de um $6$ é um evento de sucesso e qualquer outro valor é um evento de falha, nosso experimento deve seguir uma distribuição binomial de parâmetro $p$, a ideia é então encontrar o valor de $p$ tal que a nossa função massa de probabilidade seja o mais compatível possível com os dados obtidos, definimos então a nossa **verossimilhança** ou **função de verossimilhança**:

$$
P(\text{Obter o resultado 6 em 19 rolagens} \ | \ p) = \binom{100}{19}p^{19}\cdot(1-p)^{80}
$$

A ideia é então maximizar essa verossimilhança, ou seja, encontrar o valor o valor de $p$ que maximiza essa função, o que pode ser feito através do cálculo diferencial com técnicas de [[Otimização]], ou seja, derivando a função, igualando a zero e então achando os valores que satisfazem a equação, por fim, fazemos o teste da [[Derivadas de Ordem Superior|segunda derivada]] para garantir que o valor obtido é um valor máximo.

Usamos então a notação $\hat p$ para designar a **estimativa de máxima verossimilhança** do parâmetro $p$.

Um outro método para se ter em mente é tirar o logaritmo natural da nossa função verossimilhança, como o $\ln(x)$ é uma função crescente, o máximo da verossimilhança e de seu logaritmo natural coincidem. 

Por fim, no exemplo usamos a [[Função massa de probabilidade]] da distribuição para realizar a Estimativa de máxima verossimilhança por se tratar de uma [[Variável Aleatória Discreta]], mas para uma [[Variável Aleatória Contínua]], devemos utilizar a função densidade de probabilidade.



