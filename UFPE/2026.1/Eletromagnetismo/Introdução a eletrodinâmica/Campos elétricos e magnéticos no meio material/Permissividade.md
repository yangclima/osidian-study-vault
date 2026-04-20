A permissividade, denotada por $\varepsilon$ e medida em *Farads por Metro* $[F\cdot m^{-1}]$ é uma grandeza física que caracteriza a resposta de um material à aplicação de um campo elétrico.

A permissividade do vácuo é $\varepsilon_0 = 8.854\times 10^{-12} \ F\cdot m^{-1}$ onde vale a relação $\vec D = \varepsilon_0 \vec E$. Em materiais dielétricos, entretanto, a aplicação de um campo elétrico pode induzir a formação ou o alinhamento de dipolos elétricos, fazendo com que a permissividade do material difira desse valor. Esses dipolos modificam o campo elétrico efetivamente experimentado pelos átomos vizinhos e surgem da distorção que um campo elétrico provoca na distribuição de cargas dos átomos ou moléculas. Em átomos inicialmente neutros, o campo elétrico desloca ligeiramente o núcleo positivo em relação à nuvem eletrônica negativamente carregada, produzindo um pequeno deslocamento $\vec d$ entre os centros de carga e, consequentemente, um dipolo elétrico induzido. Além disso, muitas moléculas assimétricas possuem dipolos elétricos permanentes e, em líquidos e gases, tendem a alinhar-se parcialmente com o campo elétrico aplicado. Em ambos os casos observa-se um alinhamento total ou parcial dos momentos de dipolo elétrico no interior do material.

Geralmente as cargas geradas pelo alinhamento dos dipolos se cancelam internamente no meio, mas os dipolos atômicos imóveis nas superfícies externas do meio não são totalmente cancelados e portanto contribuem para o surgimento de uma densidade de carga de polarização superficial $\sigma_{sp}$.

Enquanto $\vec E$ é o mesmo, seja num meio dielétrico, seja no vácuo, como $\varepsilon_0 < \varepsilon$, o vetor deslocamento elétrico $\vec D$ difere entre os meios, associamos então essa diferença a um vetor de polarização elétrica $\vec P$, tal que:

$$
\vec D = \varepsilon\vec E = \varepsilon_0\vec E + \vec P = \varepsilon_0\vec E(1 + \chi) = \varepsilon_0\varepsilon_r\vec E
$$

Esse vetor é normalmente paralelo e na mesma direção que $\vec E$ , apontando da carga superficial de polarização negativa para a positiva, além disso, $\vec P = \vec E\varepsilon_0 \chi$  onde $\chi$ é um adimensional denominado **Susceptibilidade do Dielétrico**, sendo $< 3$ para a maioria dos átomos. É possível também definir a permissividade elétrica relativa do meio como $\varepsilon_r = 1 + \chi$.

Além disso, pode-se provar, que $\vec P$ $[C\cdot m^{-2}]$ é simplesmente o produto da densidade numérica $n$ dos dipolos como vetor momento de dipolo médio dos átomos ou moléculas $\vec p = q\vec d$ onde $\vec d$ $[m]$ é o deslocamento médio das cargas positivas com relação às negativas. Então:

$$
\vec P = nq\vec d
$$

Como sabemos, a [[Lei de Gauss]], relaciona $\vec D$ com a densidade $\rho$ mas, como agora temos dois tipos de densidade de carga: $\rho_f$ de cargas livres e $\rho_p$ de cargas de polarização podemos reescrever a Lei de Gauss como:

$$
\nabla \cdot \vec D = \rho_f 
$$

Além disso, podemos obter com o [[Teorema do Divergente]] que:

$$
\nabla \cdot \vec P = -\rho_p
$$

Quando o vetor Deslocamento elétrico varia com o tempo ele se torna uma corrente de deslocamento $\dfrac {\partial \vec D}{\partial t}$ $[A\cdot m^{-2}]$, análogo a $\vec J$.

A maioria dos dielétricos apresenta perdas quando expostos a campos elétricos oscilatórios, uma vez que  estes alteram a direção dos dipolos e suas magnitudes e parte desse movimento aquece o dielétrico, esse efeito pode ser descrito por um permissividade elétrica complexa $\underline{\varepsilon}$ dependente da frequência. Além disso, em alguns casos a permissividade elétrica depende da direção, sendo representada por uma matriz $3\times 3$ de permissividade $\overline{\overline \varepsilon}$, ou por uma matriz $3\times 3$ complexa $\underline{\overline{\overline \varepsilon}}$ caso também apresente perdas ao ser exposto a um campo oscilatório,

Um último caso são materiais denominados ferroelétricos, que são polarizados espontaneamente, mesmo na ausência de um campo elétrico externo, o que ocorre quando estes são altamente polarizáveis de maneira que a orientação de um único dipolo influencia os dipolos vizinhos a se orientarem na mesma direção formando domínios elétricos polarizados limitados pelo acúmulo de energia de campo externo ao domínio. Surgem também nos dielétricos, fenômenos parecidos com os ciclos de Histerese e o fenômeno da saturação elétrica quando todos os dipolos já estão alinhados com o campo.