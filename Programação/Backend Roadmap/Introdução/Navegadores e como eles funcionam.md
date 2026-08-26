# Fonte 01
> https://www.ramotion.com/blog/what-is-web-browser/

Com o crescimento da internet, a mídia digital se espalhou rapidamente dentro do mundo corporativo de modo que hoje, quase qualquer empresa trabalha sua presença online no objetivo de interagir com potenciais clientes e ganhar espaço nos mercados.

Nesse contexto, os `Web browsers` surgem como essenciais ferramentas para criar e gerir essa presença online, já que seu comportamento afeta parâmetros críticos para a confiança do usuário para/com a empresa, como velocidade, segurança, usabilidade e etc.

A definição de ``Web Browser`` é simples: Trata-se de um software que nos permite acessar informações na internet via ``World Wide Web``, ou seja, basicamente obter (fetch) e exibir o conteúdo de [[O que é hospedagem|páginas Web]].

Os primeiros navegadores surgiram na década de 90, com interfaces text-based muito primitivas e evoluíram com o tempo, muito dessa evolução de deve a rápida popularização da internet, computadores pessoais e da intensa competição que se estabeleceu entre as empresas que desenvolviam os principais navegadores.

O primeiro navegador, hoje chamado de Nexus, foi criado por Tim Berners-Lee (O cara simplesmente é o criador do [[O que é HTTP|HTTP]], HTML, [[Como a internet funciona|WWW]] o URL e ainda o primeiro navegador), ele também criou a primeira ferramenta de terminal que permitia navegar pelo conteúdo da Web, que serviu como base para vários navegadores que vieram depois.

A arquitetura de Web Browser é descrita brevemente pelo seguinte diagrama:

![[ber_002.png]]

A `Rendering Engine` é a parte mais essencial de um navegador, ela é a responsável por traduzir conteúdo de texto de um documento HTML em componentes na tela do usuário de acordo com seu conteúdo, as principais engines desse tipo hoje são: Blink (Google Chrome), WebKit (Safari e outros) e Gecko (Firefox, opensource).

A ``User Interface`` (UI), por sua vez, como se espera, é a parte visual do navegador com a qual o usuário interage, a barra de navegação, por exemplo.

Por outro lado,  o componente `Networking` é responsável por todo o mecanismo de `fetch` das páginas e seus componentes, solicitadas/acessadas no navegador, um dos principais componentes das web pages hoje em dia são os códigos JavaScript, que permitem gerir profundamente o comportamento dessas páginas e são processados pelo `Javascript Interpreter` (V8 no caso do Google).

Por fim, os `Security Components` são os responsáveis por todo o mecanismo de segurança dos navegadores, por exemplo, a encriptação dos dados via TSL.

Os browsers são classificados em 3 tipos:

1. Desktop browsers
2. Mobile browsers
3. Embedded Browsers (Versões limitadas dos navegadores que rodam embutidas em outras webpages e serviços)

É útil para o desenvolvedor, ter noção a respeito a cerca do funcionamento do navegador, para que assim possa otimizar seus sistemas para usufruir das características do navegador.
# Fonte 02
> https://developer.mozilla.org/en-US/docs/Web/Performance/Guides/How_browsers_work


Em geral, Websites rápidos geram experiências mais agradáveis aos usuários, eles esperam sites que carregam rápido e cuja navegação é suave, de tal modo que a atenção do desenvolvedor deve se voltar em especial para dois tópicos: A Latência e O comportamento single-threaded do navegador.

O primeiro tópico tem haver com criar páginas que carregam tão rápido quanto possível, ou ao menos aparentar que fazem isso,  de modo que o usuário recebe a informação solicitada rapidamente, para alcançar isso temos que melhorar a web performance.

O segundo tópico trata-se da compreensão de que, em geral, os navegadores são single thread, o que significa que eles executam uma tarefa por vez, isto é, quando começam uma tarefa, a executam até o final antes de passar para a próxima, o entendimento desse tópico é importante pois compreender essa natureza dos browsers permite minimizar as responsabilidades desse thread principal tornando o tempo de renderização mais suave e o tempo de resposta menor.

Ao acessar um url no navegador, por baixo dos panos estamos exxecutando as seguintes etapas:

1. [[O que é Domain Name|DNS Lookup]]
2. [[Como a internet funciona|TCP handshake]]
3. [[Como a internet funciona|TLS negotiation]]

Depois disso, finalmente o navegador recebe a response HTTP com, por exemplo, o conteúdo da página web que estava tentando acessar, o tempo entre o momento do clique até o recebimento do primeiro pacote, com normalmente 14 kB de dados é o TTFB (Time To First Byte).

Como sabemos, durante o tempo de transferência, os pacotes TCP são quebrados em segmentos, e o servidor e o cliente trocam confirmações de recebimento na forma de pacotes ACK (Acknowledgements) a cada certa quantidade de segmentos enviados, usando esse artifício, além de garantir o recebimento de todos os pacotes, o algoritmo chamado de TCP Slow Start pode ser usado para controlar a largura de bada de transferência evitando sobrecarga, basicamente, quando um pacote ACK é recebido, esse algoritmo dobra a quantidade de segmentos que podem ser enviados até recebimento do próximo ACK, caso o ACK seja perdido, ele reduz pela metade o número de segmentos. Esse número de segmentos é chamado de CWND (Congestion Window) e o algoritmo se chama TCP Slow Start por que o CWND pode começar com 1, 2, 4 ou 10 MSS (Minimum Segment Size).

Depois do recebimento completo dos dados, começa o Parsing, onde o browser processa os dados e os transforma no DOM (Document Object Model), a representação interna do layout para o navegador, e CSSOM (CSS Object Model).

Durante o parsing, o navegador processa o HTML montando a famosa árvore DOM, que representa a disposição, relacionamento e hierarquia entre os elementos do documento, esse processamento continua quando o browser encontra elementos non-blocking, como imagens, CSS, mas para quando temos scripts, especialmente os marcados com o atributo `defer`.

Enquanto o parsing ocorre, o chamado Preload Scanner realiza um lookup no documento, garantindo que os recursos críticos como os arquivos JS, CSS e as fontes sejam solicitadas antes do fim do parsing, em um menor tempo hábil.

O próximo passo é então a construção do CSSOM, uma árvore, similar ao DOM, uma estrutura de dados que expressa a relação hierárquica de estilos da página, um processo tão rápido que, poucas vezes compensa se preocupar com sua otimização e que ocorre de maneira recursiva aplicando as regras de estilo na ordem das regras mais gerais para as mais específicas.

Após isso, o processamento dos scripts JS é feito, buscando esses scripts, processando e então os compilando e interpretando em árvores abstratas de sintaxe pela engine do navegador que são passadas por um compilador que as transforma em bytecode.

Além disso, ocorre também a montagem da árvore de acessibilidade AOM que funciona como uma versão semântica do DOM.

A próxima grande etapa é a etapa de renderização, que começa pela sub etapa de Style, que une as árvores DOM e CSSOM, construídas no parsing em uma só, uma árvore de renderização que começa pelo DOM passando por cada node visível (Nós com `display: none` são pulados nessa etapa) e aplicando a eles os estilos especificados na CSSOM.

A próxima etapa é então o Layout, aqui, os tamanhos e posições dos elementos da árvore de renderização são calculados, tudo isso ocorre do root para os elementos mais abaixo na hierarquia, além disso, qualquer recálculo na posição e tamanho desses elementos é chamado de reflow.

Com o layout pronto, os elementos são finalmente exibidos na tela numa etapa chamada de Paint, por vezes, para tornar a renderização mais rápida, parte da responsabilidade é passada para a GPU e os elementos são separados em layers para facilitar possíveis re renderizações, o que é muito útil mas deve ser usado com responsabilidade por conta do custo de memória, a etapa de compositing é uma etapa adiciona que une todas as camadas.

O tempo que leva desde a requisição até a possibilidade de interação do usuário é então chamado de TTI (Time To Interactive)