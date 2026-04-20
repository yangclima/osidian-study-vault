Uma [[Funções Complexas|função]] potência complexa é uma função da forma $f(z) = z^\alpha$ onde $z$ pode ser um [[Números Complexos|número complexo]] e $\alpha$ é uma constante complexa.

Nos casos em que $\alpha$ é um inteiro ou ou uma fração $1/n$ onde $n$ é um inteiro, podemos calcular $z^\alpha$ utilizando os conceitos básicos de [[Aritmética de números complexos]] ou de [[Potências e Raízes]] de número complexos.

Um caso notável de função potência, a mais simples delas é a função quadrática complexa $f(z) = z^2$. Apesar de seus valores serem facilmente calculados, não é tão simples analisar essa função como uma [[Transformações complexas|transformação]].

Podemos então escrever $w = f(z) = f(re^\theta) = z^2 = r^2e^{2\theta}$, nesse caso, aplicar a transformação $z^2$ a um ponto $z$ equivale a aplicar nesse uma rotação  por um fator $\theta$, e uma dilatação por um fator $r$. 

> Podemos então generalizar uma função $f(z) = z^n$ como uma transformação que aplicada a um ponto $z = re^{i\theta}$ o mapeia para o ponto $w = r^ne^{in\theta}$.

É importante ressaltar que diferente das [[Transformações Lineares complexas]] uma transformação não linear pode e quase sempre altera a forma dos [[Conjuntos de pontos no plano complexo]].

Um outro caso notável de função potência é a função $f(z) = z^{1/2} = \sqrt{r}e^{iArg(x)/2}$ denominada função raiz quadrada principal e que representa o valor da [[Potências e Raízes|raiz quadrada]] de $z$, quando $k = 0$. 

Essa função potência $f(z) = z^{1/2}$ é dita **função inversa** de $g(z) = z^2$ e pode ser denotada por $f(z) = g^{-1}(z)$ e a definição de função inversa é:

> Se $f$ for uma função biunívoca (Uma função $f$ tal que dois pontos distintos tenham sempre imagens distintas, ou seja: $z_1 \neq z_2 \implies f(z_1)\neq f(z_a)$) com domínio $A$ e imagem $B$ , a função inversa de de $f$, denotada por $f^{-1}$ é a função com domínio $B$ e imagem $A$.

O que faz parecer estranho dizer que $z^n$ tem uma inversa, afinal, há mais de um ponto com a mesma imagem, entretanto, podemos dizer que ela é **biunívoca** no intervalor $[0,\infty)$ já que nesse intervalo, não existem dois pontos $z_1$ e $z_2$ com mesma imagem e por isso podemos definir $z^{1/2}$ como sua inversa nesse intervalo, dessa maneira ela age justamente de forma inversa que a transformação $z^2$, mapeando o ponto $re^{i\theta}$ para o ponto $\sqrt{r}e^{i\theta/2}$

E generalizando, definimos a função n-ésima principal como sendo

$$
z^{1/n} = \sqrt[n]{r}e^{iArg(z)/n}
$$

De modo que a função $f(z) = z^n$ é biunívoca no intervalo $-\frac \pi n < arg(z) < \frac \pi n$.