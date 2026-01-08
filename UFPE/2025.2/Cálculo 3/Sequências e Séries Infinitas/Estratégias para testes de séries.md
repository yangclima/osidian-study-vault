Até agora desenvolvemos uma série de testes para a convergência de [[Séries]], porém, aplicar todos esses testes até que um funcione não é nada prático, desenvolvemos então a seguinte estratégia para avaliar a convergência ou divergência de uma série, classificando cada série de acordo com sua forma:

1. Se a série tiver a forma de uma [[Séries Notáveis#Série harmônica|série harmônica]], ou seja $\sum 1/n^p$, sabemos que ela é convergente para $p > 1$ e divergente para $p \leq 1$.
2. Se a série tiver a forma de uma [[Séries Notáveis#Série geométrica|série geométrica]], ou seja $\sum ar^{n-1}$ ou $\sum ar^{n}$ então ela é convergente se $|r| < 1$ e divergente se $|r| \geq 1$.
3. Se a série tiver uma forma semelhante a alguma das séries notáveis (Geométrica ou harmônica), deve ser utilizado algum dos [[Testes de Comparação]], por mais que estes só se apliquem a séries de termos positivos, podemos aplicá-los a $\sum |a_n|$ testando então a [[Convergência absoluta e condicional|convergência absoluta]] da série.
4. Se para a [[Sequências|sequência]] $a_n$ o limite $\lim\limits_{n\to\infty} a_n \neq 0$ o **teste de divergência** deve ser aplicado.
5. Se a série for da forma $\sum (-1)^{n-1}b_n$ ou $\sum (-1)^{n}b_n$ o [[Teste da Série Alternada]] é a opção correta.
6. Se a série envolver fatoriais ou outro tipo de produto, a melhor opção é provavelmente o [[Teste da razão]].
7. Para séries do tipo $\sum (b_n)^n$ o [[Teste da raiz]] pode ser útil

