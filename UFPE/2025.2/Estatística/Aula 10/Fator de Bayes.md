Para uma dada hipótese $\mathcal{H}$ e dados $\mathcal{D}$, o **Fator de Bayes (FB)** também chamada de **razão de verossimilhança** é a razão das [[Estimativas de máxima verossimilhança|verossimilhanças]] da hipótese e de seu complementar, ou seja:

$$
FB = \dfrac{P(\mathcal{D}|\mathcal{H})}{P(\mathcal{D}|\mathcal{H^c})}
$$

Esse fator é muito usado na [[Atualização Bayesiana de Odds]], veja:

$$
O(D|T) = \dfrac{P(\mathcal{H}|\mathcal{D})}{P(\mathcal{H}^c|\mathcal{D})} = \dfrac{P(\mathcal{D}|\mathcal{H})P(H)}{P(\mathcal{D}|\mathcal{H}^c)P(H^c)} = \dfrac{P(\mathcal{D}|\mathcal{H})}{P(\mathcal{D}|\mathcal{H^c})} \cdot \dfrac{P(H)}{P(H^c)}
$$

Então:

$$
O(H|D) = FB \times O(H)
$$

Ou seja:

$$
\text{Odd a posteriori} = \text{Fator de Bayes} \times \text{Odd a priori}
$$

Assim, nota-se que o Fator de Bayes nos indica se os dados nos dão evidência a favor ou contra a hipótese, nesse caso:

- Se $FB > 1$ os dados nos dão evidência a favor da hipótese
- Se $FB < 1$ os dados nos dão evidência contra a hipótese
- Se $FB = 1$ os dados não nos dão evidência nem a favor nem contra a hipótese

Suponha que coletamos dados em dois estágios, primeiro $D_1$ e então $D_2$, nós vimos que a probabilidade a posteriori final pode ser obtida realizando a [[Atualização Bayesiana]] partindo da probabilidade a priori primeiro com a 
[[Estimativas de máxima verossimilhança|verossimilhança]] de $D_1$ e depois com a de $D_2$ o que funciona sempre que:

$$
P(D_1, D_2| \mathcal{H}) = P(D_1|\mathcal{H})P(D_2|\mathcal{H})
$$

Como as verossimilhanças são condicionadas pelas hipóteses nós dizemos que $D_1$ e $D_2$ são **condicionalmente independentes**, se a equação acima vale para todas as hipóteses.

 Se $D_1$ e $D_2$ são **condicionalmente independentes** para $\mathcal{H}$ e $\mathcal{H}^c$, então faz sentido considerar independentemente os Fatores de Bayes, nesse caso:

$$
BF_i = \dfrac{P(D_i|\mathcal{H})}{P(D_i|\mathcal{H^c})}
$$

Nesse caso, se a [[Odds|odd]] a priori de $\mathcal{H}$ é $O(\mathcal{H})$ a sua odd posterior a $D_1$ e  $D_2$ é dada por:

$$
O(\mathcal{H}|D_1, D_2) = BF_2\cdot BF_1 \cdot O(\mathcal{H})
$$

Resumindo, nós obtemos aqui a noção de que atualizar uma Odd com novos dados, desde que as hipóteses sejam condicionalmente independentes, consiste apenas em multiplicar a odd a posteriori atual pelo fator de Bayes dos novos dados.