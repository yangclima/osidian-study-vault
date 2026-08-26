O **LTspice** é um software gratuito de simulação de circuitos eletrônicos analógicos baseado em SPICE. Criado inicialmente pela Linear Technology e adquirido pela Analog Devices, ele permite desenhar esquemas elétricos e testar o comportamento de tensões, correntes e ruídos antes de montar a placa física.

Para começar, baixe o programa no site

https://www.analog.com/en/resources/design-tools-and-calculators/ltspice-simulator.html

Em seguida, execute o programa e crie um novo schematic, um novo projeto clicando no botão `New Schematic` ou usando o ata `Ctrl + N`.

![[pe_001.png]]

Agora, você pode adicionar seus primeiros componentes como [[Resistores Lineares|Resistores]] (Use `R` como atalho), [[Componentes Ideais|Fontes de tensão]] (Use `V` como atalho), [[Capacitores]] (Use `C`como atalho),  [[Indutores]] (Use `L` como atalho) ou um nó de referência (Use `G` como atalho) através da barra de componentes ou o atalho especifico relacionado, fazer isso ativa o uso da ferramenta respectiva ao elemento solicitado, para desativar a ferramenta, clique `Esc`, enquanto posicionando um elemento você pode usar `Ctrl + R` para rotaciona-lo.

![[pe_002.png]]

Após posicionar os seus componentes, use o botão `Wire` ou o atalho `W` para ligar os componentes usando fios, uma interessante feature é que você pode passar o fio sobre o componente passando pelas suas extremidades e o app detectará que você quer apenas ligar seus extremos.

![[pe_003.png]]

A qualquer momento você pode ainda usar o atalho `Del` para usar a ferramenta de deleção para cortar fios ou componentes do seu circuito.

O próximo passo é configurar o seu circuito, adicionar valores aos componentes, para isso, clique com o botão direito num componente e ele te permitirá editar os parâmetros daquele componente, no caso específico da fonte de tensão, utilizando o botão `Advanced` que surgirá ao clicar nela com o botão direito você pode mudar, por exemplo, a curva de tensão para uma curva senoidal.

O próximo passo é então simular o seu circuito, isso pode ser feito através do botão `Run` ou comando `Alt + R`, ao usar o comando, uma tela surgirá pedindo parâmetros da simulação, o principal parâmetro é o `Stop Time` que define o tempo de simulação, uma outra opção interessante é checkbox que diz `Start External DC Supply voltages at 0`, extremamente útil para simulação de transitórios em [[Circuitos RC]], por exemplo.

![[pe_004.png]]

Ao executar a simulação, surgirá um espaço de gráfico em branco o qual você poderá preencher utilizando medições no seu circuito, ao passar o mouse sobre qualquer ponto do seu circuito deve aparecer uma ponteira vermelha que te permitirá adicionar uma medição daquele nó ao teu gráfico.

![[pe_005.png]]

Uma outra opção é clicar e arrastar sobre um caminho de circuito, adicionando ao gráfico uma medição da diferença de tensão entre o ponto onde você clicou até o ponto onde você arrastou a ponteira.

O gráfico e sua exibição oferece várias opções para visualização dos dados, por exemplo, você pode clicar sobre o nome de uma medida para que surja um cursor através do qual você pode ver os resultados exatos da simulação para aquele valor num dado instante do tempo.

![[pe_006.png]]

Ao clicar no nome de um valor no gráfico com o botão direito você pode ainda mudar parâmetros como a sua cor e expressão (Na expressão podemos, por exemplo, adicionar `*2` para multiplicar por dois o valor exibido no gráfico ou somar a saída como uma outra medição ao usar, por exemplo `+V(n002)`) e ao clicar no próprio gráfico com o botão direito veremos opções como `Zoom to fit` que permite fazer um auto range para adaptar as medidas para serem exibidas em detalhes no gráfico.

Ao invés de clicar sobre um nó ou fio na hora de escolher uma medição para exibir no gráfico, se passarmos o mouse sobre um componente propriamente, veremos a ponteira mudar e podemos adicionar uma medição da corrente naquele componente ao nosso gráfico, uma outra opção é fazer isso pressionando `Alt`, onde adicionaremos ao gráfico uma medição da potência no componente.

Ao clicar com o botão direito sobre o eixo vertical do nosso gráfico, conseguimos mudar o seu range e seu tic para adequar a uma exibição mais específica, modificando o label do eixo.

Podemos ainda adicionar labels ao nosso gráfico usando a opção `Label Net` ou o atalho `N` adicionando um rótulo a um nó e facilitando a visualização no gráfico.

![[pe_007.png]]


