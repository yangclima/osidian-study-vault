A **Combustão** é uma [[Reações químicas|reação química]] de oxidação rápida e exotérmica que libera energia na forma de calor e luz, nesse sentido, o objetivo na engenharia é controlar essa reação para extrair dela [[Trabalho e Energia|trabalho útil]].

Essa reação será então composta por dois ingredientes fundamentais:
1. **O combustível**: A substância que será oxidada. dentre os combustíveis o nosso foco será nas moléculas cuja composição envolve apenas carbono e oxigênio e cuja formulação química é $C_xH_y$, chamados de hidrocarbonetos.
2. **O oxidante**: A substância que contém o oxigênio necessário para a reação. O oxidante mais comum é o **ar atmosférico** que, por simplicidade, consideraremos ser composto apenas por oxigênio $O_2$ ($21\%$) e Nitrogênio $N_2$ ($79\%$) de modo que a proporção é de aproximadamente $3.76$ mols de nitrogênio para um de oxigênio, isto é, um mol de ar atmosférico equivale a $\ce{1O_2 + 3.76N_2}$, apesar disso, o nitrogênio é um gás inerte e aparecerá inalterado nos produtos apesar de absorver e carregar energia térmica

o primeiro caso de combustão que veremos é o caso ideal, a **Combustão completa e estequiométrica**, completa por que todo o carbono oxida formando dióxido de carbono ($CO_2$) e todo o hidrogênio oxida formando água $(H_2O)$ e estequiométrica por que a quantidade de oxigênio fornecida é exatamente a necessária para que a combustão seja completa, sem sobra de combustível ou oxigênio após a reação, além disso a quantidade de dióxido de carbono aqui é máxima e é conhecida como $\ce{CO_2}$ estequiométrico, $\ce{CO_2}$ máximo ou máxima porcentagem teórica de $\ce{CO_2}$.

A equação geral é então:

$$\ce{C_xH_y + a(O_2 + 3.76N_2) \rightarrow bCO_2 + dH_2O + eN_2}$$

E então utilizamos os coeficientes para realizar o balanço:

1. **Balanço de carbono:** $x = b$
2. **Balanço de hidrogênio:** $y = 2d$
3. **Balanço de oxigênio:** $2a = 2b + d \implies a = x + y/4$
4. **Balanço de nitrogênio:** $e = 3.76a$

Os casos não ideais, por outro lado, são a **Combustão com excesso de ar (Mistura pobre)** e **Combustão Incompleta (Mistura rica)**, muito comuns por sinal, uma vez que a combustão estequiométrica é muito difícil de ocorrer e por isso, na maioria das vezes a queima é realizada com excesso de ar:

1. **Mistura pobre:** ocorre quando há mais oxigênio que o necessário, nesse caso, geralmente a combustão é completa e o oxigênio sobrando aparece nos produtos, esse excesso é expresso percentualmente com relação a quantidade estequiométrica, por exemplo $20\%$ de excesso quer dizer que utilizamos $1.2\times a$ de ar atmosférico.
2. **Mistura rica:** ocorre quando há menos oxigênio que o necessário para oxidar todo o carbono aparecem produtos como monóxido de carbono ($\ce{CO}$) e, potencialmente, hidrogênio ($\ce{H_2}$) e hidrocarbonetos não queimados ($\ce{HC}$).

Para descrever as reações de combustão usamos como parâmetro a relação Ar/combustível (Air-Fuel Ratio) presente na mistura, a qual pode ser descrita com base na quantidade de mols ou na massa:

1. **Base molar:** $AC_{molar} =\frac{\text{Número de mols de Ar}}{\text{Número de mols de combustível}}$
2. **Base mássica:** $AC_{massa} =\frac{\text{Massa de Ar}}{\text{Massa de combustível}}$

Para converter entre as bases podemos simplesmente multiplicar a base molar pela razão entre as massas molares de ar e combustível, ou seja, $M_{ar}/M_{combustível}$, onde tipicamente assumimos $M_{ar} \approx 28.97 \,g/mol$, isto é:

$$AC_{massa} = AC_{molar}\times \frac{M_{ar}}{M_{comb}}$$

OBS: A molaridade do oxigênio é de $32 \, g/mol$ e a do nitrogênio é de $28\, g/mol$.

Quando a classificação de misturas como ricas ou pobres, usamos como parâmetro a chamada **Razão de equivalência** $\varphi$ onde temos:

$$\varphi = \frac{AC_{estequiométrica}}{AC_{real}}$$

Ou o parâmetro Lambda:

$$\lambda = \frac{1}{\varphi}$$

Onde uma mistura rica tem $\varphi > 1$ e $\lambda < 1$ e uma mistura pobre tem $\phi < 1$ e $\lambda > 1$.


Como vimos em geral, a combustão estequiométrica é difícil e geralmente limitada pelas taxas de reação, nesse caso, por motivos econômicos quase sempre trabalhamos com excesso de ar. Em aplicações industriais o excesso de ar segue as seguintes recomendações:

- **Combustíveis gasosos:** em torno de 1 a 2%
- **Combustíveis líquidos:** entre 5 e 10%
- **Combustíveis sólidos:** em torno de 25%

Ademais, a composição dos gases de escape é crucial para análises de eficiência e emissões e em geral queremos saber a fração molar dos produtos da combustão estequiométrica e pode ser analisada de duas formas:

1. **Usando a Base Úmida (Wet Basis):** Considera todos os produtos, incluindo o vapor d’água.
2. **Base Seca (Dry Basis):** Desconsidera a água, útil pois a água geralmente con￾densa antes da medição em analisadores de gases.

 