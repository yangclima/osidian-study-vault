Diferente do [[Sistema de Ponto Fixo]], o sistema de [[Números de Ponto Flutuante|ponto flutuante]] não tem uma quantidade fixa de dígitos para cada parte inteira e fracionária do número. 

Pelo padrão IEEE754, numa máquina com um registro de $64$ bits e base $\beta = 2$, usamos um bit para o sinal, $11$ bits para o exponente e $52$ bits para a **mantissa** (também chamada de significando), além disso, temos um deslocamento $\text{BIAS}$ do expoente definido como 1023, por padrão, assim, um registro de 64 bits $s\,\epsilon_{10}\cdots \epsilon_0d_1d_2\cdots d_52$ representa:.

$$x= (-1)^sM\times 2^{e-\text{BIAS}}$$

Onde o expoente é $e = (\epsilon_{10}\cdots \epsilon_1\epsilon_0)_2$, a mantissa é $M = (1,d_1d_2\cdots n_52)_2$ (Observe que na base $2$ não é necessário armazenar o primeiro dígito, afinal ele é sempre 1, o único valor não nulo para um dígito na base 2).

Usamos o $\text{BIAS}$ de modo a representar os expoentes negativos deslocando-os de uma mesma quantidade, de forma que podemos representar os números negativos e sua ordem continua crescente, para os 11 bits do IEEE754, temos o expoente $1$ sendo $10000000000$, o $2$ sendo $10000000001$ e assim por diante e portanto a gama de expoentes é $[-1022, 1023]$.

No IEEE755 temos os expoentes $1024$ (Todos os bits como $1$) e $-1023$ (Todos os bits como $0$) reservados, o primeiro, usado para representar $\pm \infty$ caso todos os bits da mantissa sejam $0$ e ``NaN`` caso contrário, por outro lado, $-1023$ é reservado para representar o zero, caso todos os bits da mantissa sejam $0$ e um número muito pequeno se a mantissa for não nula, caso em que, não considera-se o bit implícito.