Em geral, temos um [[Tipos de Erros|erro]] [[Erro absoluto e Erro relativo|relativo]] muito pequeno associado às operações elementares no [[Sistema de ponto flutuante]], isto é, multiplicações, divisões, somas e subtrações, em geral, erros da ordem do [[Aritmética de ponto flutuante|épsilon de máquina]].

A título de exemplo, num computar de $64$ bits, temos um épsilon de aproximadamente $2,2204\times 10^{-16}$, porém, após $1000$ operações, teremos apenas uma perda de apenas 3 casas decimais de precisão.

Existe, entretanto, um caso chamado de **cancelamento catastrófico** que ocorre quando subtraímos dois números muito próximos e que leva a erros relativos gigantescos.

Alguns métodos matemáticos e algébricos podem ajudar a evitar esse erro catastrófico, isto é, evitar perda de significância. são eles:

- **Racionalização:** Quando realizamos uma subtração como $\sqrt{x^2 + 1}-1$ potencialmente teremos um erro grande, já que para valores de $x$ próximos de $0$, ocorrerá o cancelamento catastrófico, para evitar, podemos multiplica essa subtração por $(\sqrt{x^2 + 1}+1)/(\sqrt{x^2 + 1}+1)$ obtendo então, o valor como sendo igual a $(x^2+ 2)/(\sqrt{x^2 + 1}+1)$ e evitando a subtração problemática
- **Usando a expansão em série:** Uma subtração como $x-\sin{(x)}$ tem potencialmente um grande erro para valores próximos a zero, para evitar problemas com isso, podemos representar $\sin(x)$ por sua [[Séries de Taylor e Maclaurin|Série de Taylor]].
- **Usando identidades trigonométricas:** $\cos^2(x)-\sin^2(x)$ tem uma perda de significância para valores próximos a $x= \pi/4$, o que pode ser contornado ao reescrever isso como $\cos(2x)$ usando a identidade trigonométrica.