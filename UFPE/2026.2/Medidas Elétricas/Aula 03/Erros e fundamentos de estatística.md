Ao realizar medições precisaremos sempre lidar com erros e variações muitas vezes imprevisíveis na indicações obtidas, por isso, em geral, trataremos dos valores obtidos usando os [[Dispositivos de medição]] utilizando uma abordagem [[Estatística]].

Inicialmente é importante ter em mente que um [[Metrologia|erro sistemático é sempre preferível a um erro aleatório]] isso por que o erro sistemático é previsível e compensável enquanto o aleatório está fora do nosso alcance.

Para se estimar o erro sistemático, devem ser efetuadas medições repetitivas (idealmente infinitas) de um mensurando, cujo valor verdadeiro é bem conhecido, nesse caso:

$$Es = \bar I_\infty - VV$$

Onde $\bar  I_\infty$ é a média de uma série de infinitas medições e $VV$ é o valor verdadeiro atribuído ao mensurando, note porém que, na prática não temos como definir nem o valor verdadeiro da grandeza nem como fazer infinitas medições, por isso, precisamos de outra abordagem é então possível apenas realizar uma estimativa aproximada do erro sistemático, denominada de **Tendência**.

$$Td = \bar I- VVC$$

Onde $\bar I$ é a média de uma quantidade finita de medições e $VVC$ é o valor verdadeiro convencional do mensurando, uma estimativa suficientemente próxima do valor verdadeiro do mensurando.

Então uma tendência de $15g$ obtida numa série de medições da massa de um objeto nos indica que a tendência da balança é superestimar a massa dos objetos em $15$ gramas.

Podemos usar essa tendência para aplicar uma **correção** no valor da indicação, uma constante aditiva que, quando somada à indicação, compensa o erro sistemático de um sistema de medição

$$C = -Td = VVC - \bar I$$

Onde $C$ é a correção. A aplicação da correção implica na indicação corrigida.

Aplicando a correção em todos os valores de uma série de medições veremos que o erro médio provavelmente passará a ser zero  e a parcela restante de erro estará relacionada agora a um erro aleatório imprevisível que, para a $i$-ésima medição pode ser dado por:

$$Ea_i = I_i- \bar I$$

Onde $Ea_i$ é o erro aleatório na $i$-ésima medição, cujo valor é $I_i$ e $\bar I$ é a média das indicações.

Ainda nesse contexto, chamamos de **repetibilidade** a faixa de valores simétrica em torno do valor médio, dentro da qual o erro aleatório de um sistema de medição é esperado com uma certa probabilidade, Para caracterizar a repetibilidade é necessário reunir um grande número de indicações, todas obtidas de medições repetitivas do mesmo mensurando e avaliar os limites da faixa de variação, normalmente poucas indicações terão valor próximos ao limite dessa faixa de valores uma característica que vem da [[Distribuição Normal]] que está normalmente associada ao número altíssimo de [[Variável Aleatória Contínua|variáveis aleatórias]] que surgem em medições de grandezas reais.

Como características dessa distribuição normal, temos:
- Simétrica;
- Dois parâmetros caracterizam a distribuição normal: a **média** e o **[[Variância e Desvio Padrão|desvio padrão]]**;
- O ponto de inflexão caracteriza-se pela mudança de concavidade da curva;
- A distância entre esse ponto de inflexão e a média é chamada de **desvio padrão**.
- $68,26\%$ dos casos ocorrem entre $\pm \sigma$ ; $95,44\%$ ocorre entre $\pm 2\sigma$; $99,73\%$ ocorre entre $\pm \sigma$, essa característica é chamada de grau de confiança, isto é, podemos afirmar com $68,26\%$ de confiança que o erro aleatório está contido entre $\pm \sigma$

A **Incerteza padrão** é uma medida da intensidade da componente aleatória do erro de medição. Corresponde ao **desvio padrão dos erros de medição**. O desvio padrão de uma população finita na estatística, é definida como:

$$u =s = \sqrt{\frac{\sum_{i=1}^n (I_i-\bar I)^2}{n-1}}$$

Onde $s$ é o desvio padrão da amostra, $I_i$ é a $i$-ésima indicação, $\bar I$ é a média das indicações e $n$ é o número de medições repetitivas efetuadas, esse desvio padrão é também chamado de incerteza padrão $u$, além disso, chamamos $n-1$ de **graus de liberdade**.

Apesar de tudo, a análise da repetitividade é válida apenas para uma população muito grande, quase infinita, para pequenas populações usamos a distribuição de t-student cuja ideia é aplicar um “coeficiente de
segurança” que compense a estimativa pobre de um desvio padrão com pequeno grau de liberdade.

Definimos então:

$$Re = t\cdot u$$

Onde $t$ é o coeficiente de t-student para uma dada faixa de confiança e $n-1$ graus de liberdade e $u$ a incerteza  padrão calculada com $n-1$ graus de liberdade.

É possível reduzir as influências do erro aleatório quando várias medições repetidas são efetuadas e é calculada a média das indicações obtidas. Assim, temos que

$$\sigma_{\bar X} = \frac{\sigma_X}{\sqrt n}$$

onde $\sigma_{\bar X}$ é o desvio padrão da média de $n$ indivíduos, $\sigma_X$ é o desvio padrão dos indivíduos e $n$ é o número de indivíduos usados para calcular a média.

De forma similar, a incerteza padrão da média:

$$u_{\bar I} = \frac{u}{\sqrt n}$$

$$
u = \sqrt{\frac{\sum_{i=1}^n (I_i-\bar I)^2}{n(n-1)}}
$$

E da mesma forma, a repetibilidade da média:

$$Re_{\bar I} = \frac{Re_I}{\sqrt n} = \frac{t\cdot u}{\sqrt n}$$

Outro importante procedimento nesse contexto é a eliminação dos ruídos e outliers que contaminam nossos dados, para isso, uma série de procedimentos existem e são aplicados, aqui, em especial, o chamado **Método de Chauvenet**, feito seguindo os passos:

1. Calcule a média $\bar x$ e o desvio padrão $s$ das $n$ medidas
2. Determine o número de desvios padrão $r$ (d/s crítico) que a medida $x_i$ difere da média usando $$r = \frac{|x_i - \bar x|}{s}$$
3. Verifique se $r$ é menor ou igual ao $RC$ (Rejection Criterion) onde $N$ é o número de medições
4. $x_i$ é aceitável caso $r\leq RC$ onde $RC$ é o $d/s$ crítico encontrado nas tabelas

