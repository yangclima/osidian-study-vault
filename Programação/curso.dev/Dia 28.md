O dia 28 trouxe conceitos importantes, sobretudo CI/CD, de onde surgiu e que problema isso resolve, bem como as *Branching Estrategies* que consistem em formas de utilização das branches nos fluxos de trabalho.
# O processo de desenvolvimento
> Por *Dave Thomas*

## O que fazer
Segundo Dave Thomas o desenvolvimento pode ser pensado como um looping:
1. Primeiro, analise onde você está e decida para onde você quer ir
2. Depois, dê um pequeno passo em direção ao seu objetivo
3. Avalie o que aconteceu e repita o processo
## Como fazer
O segredo de aplicar bem essa estratégia é: Quando confrontado com uma ou mais escolhas, escolha a que mais facilite uma mudança no futuro.
# Desenvolvimento Waterfall
Antes do surgimento do movimento agile e do desenvolvimento dos conceitos de CI/CD um projeto de software seguia um fluxo em cascata (*Waterfall*):
$$
\text{requisitos} \rightarrow \text{projeto} \rightarrow \text{implementação} \rightarrow \text{validação} \rightarrow \text{implantação}
$$
E esse ciclo era repetido a cada feature ou conjunto de features, fazendo com que cada ciclo durasse semanas, ou até meses em projetos muito robustos, o que acabava sendo muito insatisfatório tanto para os programadores quanto para quem financiava o projeto, além de que, como a implantação só ocorria depois de uma grande gama de alterações sempre havia inúmeros conflitos que precisavam ser trabalhados e resolvidos aumentando o atrito entre as equipes de implementação e implantação. 
# Surgimento do agile
Foi então, que para resolver tudo isso, 17 programadores extremamente influentes se uniram e em 2001 lançaram o *Manifesto Agile* com uma série de ideias e conceitos para resolver os problemas do desenvolvimento no formato Waterfall, uma das principais alterações foi unir as áreas de implementação, validação e implantação em uma só, chamada de DevOps e trazer os conceitos de CI e CD, pregando a Integração contínua das alterações, a Entrega contínua dessas alterações a partir da validação e a máxima automatização das tarefas dessa etapa, trazendo consigo a o Deploy Contínuo, ou Implantação Contínua que permite a visualização das alterações em produção o mais rápido possível, satisfazendo tanto os desenvolvedores quanto os investidores.  
# Morte do Agile
Apesar do impacto grandioso do Agile, o movimento infelizmente foi corrompido por alguns problemas e dinâmicas erradas que iam, na verdade, contra as ideias iniciais do Manifesto Agile:
- Dogmatismo excessivo, o que tirava toda a flexibilidade do modelo de trabalho enchendo o fluxo de trabalho com processos massantes e complexos.
- Alta comercialização, muitas empresas se aproveitaram da ideia do movimento para vender consultorias e métodos, o grande problema é que ideias não vendem, logo, o que era comercializado eram inúmeros processos e ferramentas, indo mais uma vez contra o próprio Manifesto.
- Infantilização, algumas dessas empresas que vendiam o Agile como um produto, pregavam a infantilização dos ambientes de trabalho dos desenvolvedores, o problema é que isso era feito mesmo em detrimento da produtividade o que acabava se tornando ruim até mesmo para os próprios programadores.
# Estratégias de branching
Estratégias de branching são estratégias de formulação do fluxo de desenvolvimento utilizando [[Dia 26#Gerenciando as branches|branches]], ou seja, padronizações a cerca da utilização das branches, as três principais Branching Estrategies são *Trunk Based Development*, *Git Flow* e *Feature Branch*.
## Trunk Based Development
Essa estratégia consiste no trabalho simultâneo dos desenvolvedores numa Branch principal, fazendo commits nessa branch e evitando conflitos de merge e com a ideia de integrar o mais rápido possível,, evitando o aumento da entropia, é possível, mesmo nesse modelo, integrar features que ainda não foram totalmente concluídas, usando feature flags - Algo como uma condicional que permite o acesso a uma feature apenas para os desenvolvedores ou para grupos limitados de clientes.
## Feature Branching
Essa estratégia consiste na criação de uma nova branch para cada feature ou fix, foi popularizada pela dinâmica do GitHub, e utilização das PR's (*Pull Requests*), sendo inclusive conhecida como *GitHub Flow* e é extremamente eficiente e de fácil compreensão, o desenvolvimento da feature é feito integralmente nessa branch, até o fim.
## Git Flow
O Git flow é uma das estratégias de branching mais complexas e sua principal ideia é prover suporte para várias versões do software, ou seja, não funciona bem com CI/CD e consiste na criação de branches de desenvolvimento que periodicamente passam pelo merge na branch main, quando um conjunto de features estiver concluído.

