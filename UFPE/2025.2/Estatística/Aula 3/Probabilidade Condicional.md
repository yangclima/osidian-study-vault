A **Probabilidade Condicional** responde a seguinte questão: Como muda a probabilidade de um [[Conceitos de Probabilidade|evento]] se nós tivermos uma informação extra?

Por exemplo, dados dois lançamentos sucessivos de uma moeda, qual a probabilidade de saírem duas caras? nosso espaço amostral, nesse experimento é $\Omega = \{CC,CO, OC, OO\}$ (Cara é $C$ e $O$ é coroa), logo a probabilidade de saírem duas caras é ${1}/{4}$.

Agora pensemos: Sabendo que o primeiro lançamento resultou em cara, qual a probabilidade de saírem duas caras? Nesse caso começamos a operar em uma espaço amostral $\Omega^\prime \subset \Omega$, onde estão relacionados os possíveis resultados que seguem a definição do problema ("o primeiro lançamento resultou em cara"), logo $\Omega^\prime = \{CC, CO\}$, nesse caso, a probabilidade de obtermos duas vezes cara deixa de ser $1/4$ e passa a ser $1/2$, isso é a chamada Probabilidade Condicional.

A notação para essa probabilidade é a seguinte:

$$
P(A|B)
$$

Essa notação pode ser lida como "Probabilidade de $A$ tal que $B$", ou seja, a probabilidade do evento $A$ ocorrer, dado que o evento $B$ ocorreu.

Perceba o que falamos no nosso exemplo, calcular a probabilidade condicional de um evento é restringir o nosso espaço amostral aos eventos onde $B$ ocorreu e dentro desse novo espaço amostral buscar a probabilidade do nosso evento de interesse $A$, dessa maneira, podemos definir formalmente a probabilidade condicional como:

$$
P(A|B) = \dfrac{P(A \cap B)}{P(B)}
$$

Ainda usando essa definição, podemos chegar a chamada **Regra da multiplicação**:

$$
P(A \cap B) = P(A|B)\cdot P(B)
$$