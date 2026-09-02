Uma **norma** pode ser utilizada para quantificar erros e medir distâncias num [[Espaços vetoriais|espaço vetorial]], sendo uma operação denotada por $||\cdot||$ e definida no $\mathbb R^n$ que associa a cada elemento  $x\in \mathbb R^n$ um escalar $||x||$  e que possui as propriedades a seguir:

1. $||x|| > 0$ para todo $x\in \mathbb R^n$
2. $||x|| = 0$ se e somente se $x=0$
3. $||\alpha x|| = |\alpha|||x||$ para todo $\alpha\in \mathbb R$ e $x\in \mathbb R^n$
4. $||x+y||\leq ||x|| + ||y||$ para todo $x,y \in \mathbb R^n$  (Desigualdade triangular)
5. $|x^Ty| \leq ||x||||y||$ para todo $x,y\in \mathbb R^n$ com a igualdade sendo satisfeita somente se $x$ for um múltiplo de $y$ (Desigualdade de Cauchy-Schwarz)

Existem diferentes operações que satisfazem essas condições e por isso existem então múltiplas normas, a mais comum é a **Norma euclidiana**, também chamada de **norma**-$l_2$ definida como:

$$||x|| = ||x||_2 = \sqrt{x^Tx} = \left( \sum_{i=1}^n|x_i|^2\right)^{1/2}$$

Temos também a **norma infinita** $||x||_\infty$ ou **norma**-$l_\infty$, definida como:

$$||x||_\infty = \max_i |x_i|$$

E ainda a chamada **norma unitária** também chamada de **norma**-$l_1$ definida como:

$$||x||_1 = \sum_{i=1}^\infty |x_i|$$

Sendo todas as normas definidas acima casos especiais da chamada **norma**-$l_p$ de Hölder, definida como:

$$||x||_p = \left(\sum_{i=1}^n|x_i|^p\right)^{1/p}$$

Em geral, exceto quando houver indicação contrária, $||x||$ denotará a norma euclidiana.