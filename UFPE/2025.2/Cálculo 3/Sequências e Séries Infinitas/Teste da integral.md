Na maioria das [[Séries]] notáveis que conhecemos o limite e o valor para o qual convergem esse valor é obtido através da modelagem de uma expressão para a $n$-ésima soma parcial dessa série, esse processo, no entanto, é muito complicado na grande maioria dos casos, dessa maneira, é conveniente desenvolver uma séria de testes que nos permitam avaliar a convergência ou divergência de uma série, vale notar que esses testes não nos fornecem o valor para o qual a série converge mas apenas o seu caráter de convergência ou divergência.

O primeiro desses teste é o **teste da integral**.

Seja $f$ uma função contínua, positiva e decrescente com domínio $[1,\infty]$ e seja $a_n = f(n)$ o $n$-ésimo termo de uma [[Sequências|sequência]], então a série $\sum_{n=1}^\infty a_n$ é convergente se e somente se a integral imprópria $\int_1^\infty f(n)$ for convergente.

$$
\text{Se }\int_1^\infty f(n) \text{ converge} \implies \sum_{n=1}^\infty a_n \text{ é convergente}
$$
$$
\text{Se }\int_1^\infty f(n) \text{ diverge} \implies \sum_{n=1}^\infty a_n \text{ é divergente}
$$

