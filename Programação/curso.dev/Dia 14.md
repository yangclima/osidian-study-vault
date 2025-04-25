O dia 14 aborda mais algumas noções sobre planejamento e execução de projetos, complexidade de código e arquitetura de software.
# Atracando ás cegas
Imagine que você está num barco, um grande navio de cruzeiro e precisa atracar, porém, uma grande névoa te impede de ver a costa, o que você faz? Move o barco para norte, sul leste e oeste para encontrar a costa? Bem, isso culminaria numa gigantesca perda de energia, mas o que fazer então? Mande botes que possam identificar a costa e um bom lugar para atracar, gastando pouca energia e ainda acelerando a identificação, essa é uma analogia para o inicio de um projeto, você ainda não sabe exatamente a direção correta em que precisa ir, ou pelo menos não totalmente, pois bem, ao invés de desde o início atacar o projeto com todas as suas forças, envie os barquinhos, crie uma PoC (*Proof of Concept*) ou várias delas,  o ideal é que elas sejam baratas e rápidas de se produzir, e que possam de fato mostrar a direção correta.

Tendo então descoberto a direção correta, cuidado, não da pra saber se há um recife de corais que pode afundar seu navio, então, não ligue os motores a força total, mesmo que você saiba que aquela é a direção, vá devagar, crie um MVP (*Minimum Viable Product*), que possua as features básicas da sua proposta e veja como ele se desenrola ou aplica.
# Fundação
A primeira milestone do projeto, é a sua fundação, fazer uma boa fundação é essencial para o desenrolar do projeto e fazer boas escolhas aqui, permitirá criar uma fundação forte que servirá para o seu propósito e te dará suporte para ocasionalmente expandir sua proposta.

Uma boa dica é começar pelo frontend, afinal, isso é a única coisa concreta para o usuário, e da visão dele, o resto da aplicação não passa de detalhes técnicos.

Os principais pontos desse passo do projeto são:
1. Proposta de arquitetura de software e estrutura de pastas
2. Testes automatizados
3. Banco de dados (local)
4. Migrations
5. Continuous Integration
6. Linter de código (Checagem lógica, ao invés de estilística como no [[Dia 10#Configurando o Prettier|Prettier]])
7. Linter de commits
8. Banco de dados (Produção e homologação)
9. Tipo da licença
# Over e underengineering
Durante a carreira de um programador, seu código evolui muito e a ânsia por testar novas noções e ferramentas faz com que a complexidade do seu código aumente exponencialmente, mas ao ganhar maturidade essa complexidade tende a diminuir estabelecendo-se numa faixa ótima acima do underengineering e baixo do overengineering, e assim deve ser.

Pensando nessa lógica, o programador deve criar seus projetos como num corte de cabelo, se cortarmos pouco, sempre podemos voltar e cortar um pouco mais, porém, se cortarmos muito, é impossível voltar atrás, essa é a lógica, fazer algo simples sempre permite colocar mais um tijolinho e seguir a construção, criar novas features por que as existentes não estão sendo suficiente mas o contrário, ou seja, faze inúmeras features e perceber que está praticando overengineering e ter que podar seu projeto significa trabalho perdido.

O grande segredo de um projeto de software é, portanto, ser **modificável**, versátil, responde bem às mudanças que se mostrarem necessárias durante seu desenvolvimento, esse é o ponto chave.
# Arquitetura e pastas
Visando atingir os preceitos definidos até agora, sobretudo o fato do software ser versátil e modificável é que entramos na discussão sobre a arquitetura a ser usada no projeto e a organização de pastas do repositório.

Primeiro, vale salientar, que arquitetura de software e estrutura de pastas são mundos diferentes, a arquitetura é definida pelo escopo dos componentes e e o tipo de relação entre eles, já a estrutura de pastas é só uma divisão conveniente para facilitar o processo de encontrar as partes do nosso sistema.
# Arquitetura MVC
A o padrão arquitetural MVC (*Model View Controller*) é um padrão extremamente maduro criado em 1979 e consiste, não surpreendentemente na divisão das responsabilidades entre os seguintes tipos de componentes:
## Model
O Model representa os dados que serão exibidos na View, é portanto uma coleção de classes que descreve a lógica de negócios (Modelo de negócios e modelo de dados) e também as regras de negócios para os dados, ou seja, como eles serão alterados e manipulados.
## View 
A View representa os componentes da interface gráfica, sua responsabilidade é exibir os dados recebidos do Controller, no MVC, a View monitora o Model em busca de qualquer alteração de estado e exibe o modelo atualizado. O Model e a View interagem através do padrão Observer.
## Controller
O Controller é responsável por processar as solicitações recebidas. Ele processa os dados do usuário por meio do Model e retorna os resultados para a View. Normalmente, ele atua como um mediador entre a View e o Model.
# Estrutura de pastas
```
📦 root
 ┣ 📂 pages
 ┃ ┗ 📜 index.js
 ┣ 📂 models
 ┃ ┣ 📜 user.js
 ┃ ┣ 📜 content.js
 ┃ ┗ 📜 password.js
 ┣ 📂 infra
 ┃ ┗ 📜 database.js
 ┃ ┣ 📂 migrations
 ┃ ┣ 📂 provisioning
 ┃ ┃ ┣ 📂 staging
 ┃ ┃ ┣ 📂 production
 ┣ 📂 tests
```
