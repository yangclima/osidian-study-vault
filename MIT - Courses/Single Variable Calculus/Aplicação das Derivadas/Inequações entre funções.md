Inequações entre funções são ferramentas muito úteis para entender o crescimento e dimensionamento de funções que possuem termos complexos. Se quisermos estudar a função $f(x) = 1 + \frac{x}{2} - \sqrt{1 +x}$ por exemplo, podemos nos aproveitar das implicações do [[Teorema do Valor médio|TVM]], e proceder da seguinte forma:
1. Primeiro, notamos que para $x = 0$, $f(x) = 0$. Restringindo o nosso estudo para $x \leq -1$
2. Pelo TVM temos: $$f(x) = f(0) + f^\prime(c)(x-0)$$$$1 + \frac{x}{2} - \sqrt{1 +x} = [\frac{1}{2} - \frac{1}{2\sqrt{1 + c}}]\cdot x $$
3. Analisando o resultado, podemos concluir que, para $x > 0$, já que $c$ está entre $a$ e $x$: $$\frac{1}{2} > \frac{1}{2\sqrt{1 + c}}$$
4. Concluímos então que para $x > 0$, $f(x) > 0$ e consequentemente: $1 + \frac{x}{2} > \sqrt{1 +x}$
