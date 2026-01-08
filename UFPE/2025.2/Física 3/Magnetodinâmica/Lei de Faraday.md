Como vimos, uma [[Corrente|corrente]] fluindo em um condutor gera um [[Campo Magnético]], entretanto, olhando mais a fundo, microscopicamente, essa corrente nada mais é que um série de cargas colocadas em movimento pela ação de um [[Campo Elétrico]], então, considerando que podemos gerar um campo magnético aplicando um campo elétrico num condutor, poderíamos então gerar um campo elétrico aplicando um campo magnético nesse mesmo condutor? Perceba que essa pergunta é sobre a simetria desse fenômeno físico.

Essa resposta foi respondida por **Michael Faraday** em 1831, e a resposta é positiva, ao aplicarmos sobre um condutor um **campo magnético que VARIA NO TEMPO**, um campo elétrico será gerado e causará o movimento das [[Carga|cargas]] presentes no condutor, e portanto, uma [[Corrente|corrente]] será induzida, esse fenômeno recebe o nome de **indução eletromagnética**.

Perceba que destacamos o fato de que para que um campo elétrico seja gerado, o campo magnético aplicado sobre o condutor deve variar no tempo, essa é uma das principais conclusões que Faraday obteve, utilizando uma espira conectada a um galvanômetro (Dispositivo que mede correntes elétricas de baixa intensidade) e uma barra magnética ele chegou a conclusão que nenhuma corrente é induzida se barra estiver parada com relação a espira ($\vec B$ constante no tempo) e que durante a aproximação do imã a corrente induzida é contrária à corrente induzida durante seu afastamento.

Para definir matematicamente esse fenômeno, precisamos do conceito de [[Fluxo magnético]], e então enunciamos a lei de Faraday como:

$$
\varepsilon = -\dfrac{d\Phi_b}{dt}
$$

Interpretando essa equação, chegamos a conclusão qualitativa do fenômeno da indução eletromagnética: Dada uma espira condutora submetida a um campo magnético $\vec B$, e portanto a um fluxo magnético $\Phi_B$, se a taxa de variação temporal desse fluxo for diferente de $0$, surgirá na espira uma [[Força eletromotriz]] $\varepsilon$ cuja magnitude é igual a taxa de variação instantânea desse fluxo no tempo.

Algo interessante de se notar é que a lei de Faraday é o mais genérica possível na tratativa da indução, a força eletromotriz que surge é função da variação temporal do fluxo magnético e este, por sua vez, pode variar seja a partir do movimento da espira, seja a partir da mudança na magnitude ou direção do campo magnético, ou mesmo por uma variação na direção ou magnitude do vetor de área numa espira girando ou de uma espira cuja área varia no tempo.

É muito comum que utilizemos a notação integral/diferencial para definir ou denotar esse fenômeno:

$$
\oint \vec E \cdot d\vec s = -\dfrac{d}{dt}\iint \vec B\cdot d\vec A
$$

Essa notação é importante por que tira de cena a necessidade da existência de uma espira ou material condutor para que o fenômeno se manifeste e nos dá consciência de a lei de Faraday é muito mais do que apenas sobre uma corrente induzida, e sim sobre uma relação intrínseca entre o campo magnético e o campo elétrico, independente do material, meio ou espaço.

Um outro fato a se atentar é que quando a derivada temporal do fluxo magnético é diferente de $0$, a [[Integrais de linha|integral de linha]] do campo elétrico sobre uma curva fechada é também diferente de $0$ o que pode parecer estranho, já que todos os [[Campo Elétrico|campos elétricos]] que vimos até agora eram conservativos, afinal $\vec E$ é ou não conservativo? A resposta é "depende", os campos elétricos eletrostáticos, ou seja, gerados por cargas estacionárias, é conservativo, seu [[Rotacional]] é nulo, para os campo elétricos eletrodinâmicos, isso não é bem verdade, o rotacional é não nulo e portanto, o campo não é conservativo.