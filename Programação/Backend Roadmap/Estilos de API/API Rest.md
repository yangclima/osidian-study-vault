# Fonte 01
> https://www.redhat.com/en/topics/api/what-is-a-rest-api

Uma API (Application Programming Interface) é basicamente um conjunto de definições e protocolos para construir e integrar aplicações de software, algo como um contrato entre provedor e um usuário estabelecendo restrições a respeito do conteúdo enviado e recebido por cada um, em outras palavras, basicamente, quando você precisa se comunicar com um computador, é a API que permite que você comunique para o servidor o que você quer de modo que ele entenda e retorne as informações que você quer, um mediador entre o cliente e os web services com a vantagem de que, para utilizá-la você não precisa saber dos detalhes de implementação interna dos servidor.

A API REST, por sua vez é uma API que implementa os princípios de design do padrão arquitetural REST (Representational State Transfer), um conjunto de regras e restrições, de modo que esse padrão pode ser implementado de múltiplas maneiras.

Quando um cliente faz um requisição para uma API RESTful, ela retorna uma representação do estado atual do recurso solicitado através do protocolo [[O que é HTTP|HTTP]] em um dos formatos suportados, normalmente, o JSON (Java Script Object Notation), por esse formato ser agnóstico e legível tanto por humanos quanto por máquinas.

Nesse padrão de design, os parâmetros e headers da requisição (E também da response) HTTP são também muito importantes, trazendo dados e informações como o URI (Uniform Resource Identifier), metadados, autorização, cache, cookies e muito mais

Para ser considerada RESTful, uma API precisa seguir os seguintes critérios e princípios:

1. Deve possuir uma arquitetura cliente servidor com requisições manipuladas através do protocolo HTTP.
2. Possuir uma comunicação cliente servidor stateless, sem informações dos usuários sendo armazenadas entre requests e onde cada requisição é isolada e independente.
3. Possuir um sistema de cache que otimiza as interações entre cliente e servidor
4. Ter uma interface uniforme entre os componentes garantindo que as informações sejam transferidas num formato padrão, seguindo:
	- Os recursos solicitados são identificáveis e distintos das representações enviadas para o cliente
	- Os recursos podem ser manipulados pelo cliente através da representação enviada para ele por que ela possui informações suficientes para isso
	- Mensagens auto descritivas retornadas pelo servidor tem informações suficientes para descrever como o cliente deve processá-las
	- Hipertexto e Hipermídia estão disponíveis, de modo que o cliente, após acessar um recurso deve conseguir usar hiperlinks para encontrar e performar todas as próximas ações  disponíveis
5. Um sistema em camadas que organiza cada tipo de servidor envolvido na busca das informações em camadas invisíveis ao usuário.
6. A habilidade (Opcional) de enviar código executável quando solicitado, estendendo as funcionalidades do cliente.

Apesar dessa série de exigências, o padrão REST ainda é consideravelmente mais simples e amplo que outros como o SOAP que fazem exigências e impõem restrições  muito mais específicas e duras.

Uma API REST, em contraste, é menos exigente, como uma série de diretrizes que podem ser implementadas quando necessário que as torna mais leves, rápidas e escaláveis.

# Fonte 02:
>https://learn.microsoft.com/en-us/azure/architecture/best-practices/api-design

Como já vimos, uma API  web RESTful é aquela que implementa os princípios de arquitetura REST para construir uma interface stateless e desacoplada entre cliente e servidor com requisições manipuladas usando HTTP e retornando representações de recursos que contém links de hipermídia e códigos de status HTTP.

Uma API RESTful deve ainda ser independente de plataforma, de modo que os clientes podem interagir com sua interface web sem se preocupar com sua implementação interna e, além disso, ser desacoplada, de modo que cliente e servidor podem evoluir independentemente.

Nesse sentido, cabe destrinchar alguns dos princípios do REST enquanto aprendemos as melhores práticas de arquitetura e codificação voltadas a esse padrão de API.

## URI de recursos
Uma API RESTful é organizada em torno dos recursos e para organizar seu design definimos URIs que correspondem e mapeiam os endpoints para as entidades de negócios, e para nomear esses URIs, é recomendado seguir as seguintes convenções:

1. Use substantivos ao invés de verbos para identificar os recursos, por exemplo, `orders` ao invés de `create-order`, os métodos HTTP já deixam clara a ação a ser performada
2. Use substantivos no plural para referenciar coleções construindo uma hierarquia entre coleções e itens individuais, por exemplo, `/users` para identificar a coleção de usuários e `/users/{id}` para identificar um usuário específico
3. Considere a relações entre as entidades da aplicação nos identificadores, por exemplo, podemos identificar os pedidos de um usuário específico usando `/users/{id}/orders`, entretanto, usar muitos relacionamentos na mesma URI pode ser complicado e trabalhoso
4. Use relações simples e flexíveis nos URIs, em geral, com no máximo 3 partes. Usar um URI como `/users/91/orders/13/products` é complexo e inflexível numa possível mudança das relações das entidades, ao invés disso prefira identificadores simples, como `/users/91/orders` já que os usuários podem usar as informações recebidas para buscar outras informações em um outro URI como `/orders/13/products`
5. Evite uma API com muitos pequenos recursos e entidades, isso infla o número de requisições e como cada requisição leva algum tempo isso pode gerar mais latência, mas cuidado, ter recursos muito grandes também é um problema e pode gerar gerar problemas então é importante balancear essa divisão
6. Evite criar URIs que espelham a estrutura interna do servidor, usar um estado representativo é justamente a principal ideia do REST, ter uma tabela com um determinado nome na base de dados não significa que você precisa expor um endpoint com esse nome, na verdade, isso aumenta a superfície disponível para ataques virtuais

> Alguns endpoints são extremamente complexos de modelar usando o padrão REST, isto é, como recursos, nesses caso, um outro padrão emerge, muitas vezes chamado de RCP (Remote Call Procedure) e os endpoints podem ser nomeados como verbos (Funções) e os parâmetros, caso necessários, podem ser passados como query parameters, mas em um API REST isso deve ser usado com moderação.

## Métodos da API
A arquitetura REST segue a definição dos métodos do protocolo HTTP, sendo os  métodos mais comuns o ``GET``, ``POST``, ``PUT``, ``PATCH`` e ``DELETE``, cada um especificando uma operação distinta que deve ser observada na implementação dos endpoints da API de maneira consistente com sua definição no protocolo, o recurso que está sendo acessado e a ação que está sendo performada. 

Em especial, é importante se atentar que o efeito de cada método depende se o recurso é um item individual ou um coleção e também que apenas os métodos que realmente fazem sentido em cada cenário precisam e devem ser implementados.

A descrição de cada método, detalhes e ação performada estão descritas na seguinte tabela:


| Método   | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                               |
| -------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `GET`    | O método ``GET`` é utilizado para recuperar a representação de um recurso na URI especificada, representação essa, retornada no corpo da resposta e contendo detalhes do recurso solicitado.                                                                                                                                                                                                                                            |
| `POST`   | O método `POST` é utilizado para criar um novo recurso ou para submeter dados para processamento a um recurso existente, caso crie um novo recurso, idealmente, a URI gerada por esse servidor para o novo recurso deve ser retornada para o cliente.                                                                                                                                                                                   |
| `PUT`    | O método `PUT` é utilizado para atualizar todas as informações de um recurso existente, ou, em alguns casos, criar um novo, caso ele não exista (Isso depende do caso de implementação e de uma avaliação da capacidade do usuário de definir a URI de um novo recurso), uma característica importante do `PUT` é a idempotência, requisições idênticas devem retornar sempre o mesmo resultado.                                        |
| `PATCH`  | O método `PATCH` é utilizado para realizar uma atualização parcial de um recurso, e sua implementação exige o chamado "patch document" que são basicamente as especificações de como realizar o update do recurso, o modelo mais comum para isso é o chamado `JSON merge patch` onde são fornecidos no body da request apenas os campos que precisam ser atualizados e onde não é especificada uma ordem para a atualização do recurso. |
| `DELETE` | O método `DELETE` é utilizado para excluir um recurso numa URI específica.                                                                                                                                                                                                                                                                                                                                                              |
## Tipos MIME 
A "representação" de um recurso é a forma como esse recurso, identificado por uma URI é codificado e transportado através do protocolo HTTP num formato específico, especificado usando media types, também chamados de MIME Types, definidos no header `Content-Type` na resposta do servidor ou na requisição do cliente, exemplos de valores para esse header são `application/json` e `application/xml`. 

Se o cliente fizer uma requisição para o servidor usando um media type que o servidor não suporta, o status code retornado deve ser `415 (Unsupported Media Type)` e ocasionalmente o cliente pode especificar numa requisição, que media types ele aceita na resposta usando o header `Accept`, com uma lista dos media types aceitos, caso o servidor não consiga resolver num dos formatos aceitos um status code ` 415 (Unsupported Media Type)` deve ser retornado.

## Endpoints Assíncronos
Se uma operação é extremamente longa de modo que seria inviável retornar seu resultado na resposta da requisição que desencadeou sua execução, podemos implementar um endpoint assíncrono, basicamente, seguimos os passos:

1. Quando o cliente faz uma requisição válida para o endpoint assíncrono, ele responde essa requisição com um `202 (Accepted)` indicando que a requisição foi aceita e a ação foi iniciada no servidor, além disso, usamos um header `Location` nessa response com o valor de uma URI por onde o cliente pode acompanhar a execução da task
2. Se o cliente der um `GET` contra o endpoint fornecido no header `Location` na inicialização da task, a resposta do servidor deve conter o status atual da execução da tarefa e pode conter um tempo estimado até o fim da execução ou um URI que permita cancelar a ação.
3. Ao finalizar a ação, o ``GET`` contra a URI de status da tarefa deve indicar sua conclusão e caso a tarefa crie um recurso, a API deve retornar um status code `303 (See Other)` com uma URI para o novo recurso no header `Location`

## Filtros e Paginação de dados
Para reduzir o tamanho do payload e otimizar a obtenção de dados podemos implementar como features a paginação de dados e o query-based filtering, permitindo que os clientes busquem apenas os dados nos quais realmente tem interesse.

A **paginação** divide longas coleções de dados em grupos menores e manipuláveis, podendo ainda aceitar query parameters como `limit` para especificar o tamanho dos pacotes e `offset` para especificar o parte da coleção que está sendo buscada, com valores padrão significativos para cada parâmetro (`limit` sendo algo como 50 ou 100 itens e `offset` sendo 0).

A **filtração de dados** permite que os usuários refinem os dados buscados aplicando condições à busca, que dependem do recurso e domínio da aplicação, com query parameters que façam sentido dentro do contexto.

A **ordenação** também é uma possibilidade e permite que os usuários busquem pelos dados numa determinada ordem, mas pode ter efeitos negativos sobre o mecanismo de cache da aplicação.

**Seleção de campos** também pode ser interessante, permitindo que o usuário  especifique os campos dos recursos nos quais está interessado.

Vale notar que a implementação de qualquer uma dessas opções tem que ser bem pensada e os valores dos filtros devem ser bem validados.
## Respostas parciais
Em alguns casos em que um endpoint retorna grandes campos binários como imagens, pode ser implementada a feature de respostas parciais, basicamente, seguimos:
1. Primeiro, o método `HEAD` (Uma ação perfeitamente igual ao `GET` mas onde o body da response não é transmitido) é permitido e retorna uma resposta sem body mas especificando o tamanho do recurso com o header `Content-Length` e que aceita requisições parciais com o header `Accept-Ranges`
2. O cliente, observando o valor do tamanho total do recurso faz a requisição `GET` especificando com o header `Range` que parte dos bits do recurso ele quer receber
3. O server responde com a response parcial especificando com `Content-Length` o tamanho dos dados enviados e com `Content-Range` a parte do recurso que esses bits representam e com o status code `206 (Partial Content)`

## HATEOAS
Uma das principais ideias do REST é a possibilidade de navegar pelo sistema e utilizar todas as suas funções sem necessitar de nenhum conhecimento prévio sobre o seu esquema de URIs, de modo que a resposta a cada requisição `GET` deve conter os hiperlinks para recursos e ações diretamente ligados ao recurso solicitado, num princípio chamado HATEOAS (Hypertext as the Engine of Application State) que cria faz com que, na prática, o sistema se comporte como uma [[Máquinas de Estado|máquina de estado finito]] e a resposta para cada requisição contenha a informação necessária para se mover de um para o próximo estado.

Não existem, em geral, padrões globais de implementação do HATEOAS de modo que ele é flexível para cada cenário específico, mas uma ideia comum é retornar um objeto `links` na resposta JSON com cada item desse objeto representando um link para uma ação que pode ser feita contra o próprio recurso retornado ou contra um dos recursos que se relacionam com ele e outras informações relevantes sobre. Em geral o conjunto de links pode mudar dependendo das ações válidas para cada estado do recurso.
## Versionamento
Uma API Web não permanece estática durante todo o seu ciclo de vida, as implementações mudam, as regras de negócios mudam e ocasionalmente o relacionamento entre os recursos também mudam, na medida que essas mudanças afetam o comportamento e as regras da API pode ser fazer necessário mudar os URIs as regras definidas para corpos de resposta e requisição e muito mais, o problema é que esse tipo de alteração pode quebrar a implementação das aplicações externas que consomem a API, como solução para isso, surge o versionamento, que pode ser feito de várias formas diferentes:

1. `No Versioning` é uma opção que consiste em não fazer versionamento e tomar os cuidados necessários para não quebrar as implementações, evitando remover ou renomear campos nas respostas ou das requisições, e ocasionalmente adicionando novos campos na resposta, considerando que implementações antigas vão ignorá-los e as novas passarão a tratá-los
2. `URI Versioning` (Ou `Path Versioning`) é  uma outra opção de versionamento, consistindo em adicionar uma designação da versão no URI do recurso por exemplo, a primeira versão do endpoint `/users` fica em `/v1/users` e a segunda em `/v2/users` e assim por diante, o problema é que o servidor fica responsável pelo roteamento das requisições para a versão correta e isso também pode complicar  a implementação do HTEOAS.
3. `Query String Versioning` é mais uma opção nesse sentido e consiste em versionar usando um query parameter, por exemplo, para acessar a primeira versão do endpoint de usuários, usamos `/users?version=1` o problema , mais uma vez, é responsabilizar o servidor pelo roteamento das requisições para a lógica correta e atrapalhar a implementação do HATEOAS, outro problema pode surgir com esse método em navegadores antigos, que não realizam caching para endpoints com query parameters  
4. `Header Versioning`, uma outra opção de versionamento, consiste em versionar utilizando um header personalizado na requisição, por exemplo `api-version: 2` seria usado numa requisição que quer acessar a versão 2 da API, apresentando URIs limpas mas o mesmo problema com o HATEOAS.
5. `Media Type Versioning` é o último tipo de versionamento e utiliza para tal o header `Accept`, já que é possível criar tipos de media personalizados, então, podemos usar, por exemplo o header `Accept: application/vnd.example.v2+json` que queremos acessar a versão dois da ``API``, esse método é mais adequado ao HATEOAS.

Vale notar que escolher um estilo de versionamento não é uma questão estética, mas tem, na prática, diversas implicações na dinâmica da API, sobretudo sobre o sistema de cache da aplicação, em especial, o métodos de `URI Versioning` e `Query String Versioning` são cache-friendly já que é fácil para os servidores de cache identificar a diferença entre as requisições, por outro lado, ao implementar `Header Versioning` ou `Media Type Versioning` é complicado integrar com um sistema de cache eficiente
## API Multitenant (Multi locatário) 
Algumas API's são construídas para múltiplos clientes diferentes que usarão de maneiras distintas a aplicação, como um prédio, a mesma fundação servindo a múltiplos andares diferentes, nesse caso, como a existência de múltiplos clientes diferentes afeta significantemente a estrutura e funcionalidade da API, é essencial pensar nesse compartilhamento de de infra desde a concepção inicial do projeto, para garantir o funcionamento concorrente de serviços como autenticação, autorização e isolação dos dados e camadas da aplicação.

Para controlar o fluxo de dados entre os múltiplos clientes, existe diferentes estratégias, sendo as principais:

1. `DNS Resolution`: É a isolação no nível de DNS, usamos subdomínios ou domínios para isolar o fluxo de dados de cada cliente, o que necessita da aplicação do conceito de [[DNS e como ele funciona|DNS resolution]] para a resolução dos domínios e nesse modelo é essencial compartilhar o mesmo host name entre o back-end e o proxy reverso para evitar problemas de redirecionamento
2. `Headers`: Uma outra opção para a isolação dos clientes é usar uma identificação nos headers da requisição, o que pode facilitar a configuração no lado do cliente, mas oferece problemas com o sistema de cache, um exemplo de implementação desse tipo é o uso do header `Authorization` com os JWT Tokens
3. `URI Path`: Uma outra abordagem é utilizar identificadores específicos no URI do recurso, adicionando algo como `/tenants/tenant-name` no início da URI dos recursos a serem acessados

## Rastreamento Distribuído
As arquiteturas de API modernas, como microserviços trazem algumas problemáticas difíceis de lidar, em especial quando nos referimos a tratamento de erros e rastreamento de requisições, nesse sentido, uma solução que emergiu envolve o uso de headers de requisição para identificar uma requisição específica no ecossistema, como `X-Trace-ID`, `Correlation-ID` ou `X-Request-ID` para propagar o contexto de rastreamento entre os endpoints, facilitando a identificação de falhas, monitoramento de latência, e mapeamento das dependências.

As APIs que suportam esse tipo de monitoramento melhoram seu nível de observabilidade e capacidade de debug permitindo uma compreensão mais granular do sistema como um todo e seu comportamento tornando-o fácil de entender, diagnosticar e resolver problemas.

## Nível de maturidade das APIs Web
Em 2008, Leonard Richardson propôs o que hoje é conhecido como RMM (Richard Maturity Model) para API's web, definindo quatro níveis de maturidade para uma API Web baseados nos princípios do REST como uma guideline arquitetural, nesse modelo, quanto maior o nível de maturidade da API, mais Restful a API é e mais próxima da idealidade de atendimento ao REST ela fica, são os níveis:

0. Definem uma URI e todas as operações são requisições ``POST`` contra esse endpoint. 
1. Cria URIs separados para cada recurso
2. Usa métodos HTTP para definir as operações sobre cada recurso
3. Usa HATEOAS

# Fonte 3
> https://restapitutorial.com/

Tecnicamente REST é um acrônimo para "REpresentational State Transfer"  que se trata basicamente de um estilo arquitetural inicialmente criado por Roy Fielding na sua [tese de doutorado](https://roy.gbiv.com/pubs/dissertation/fielding_dissertation.pdf).

As definições da tese de Roy precisam ser seguidas para que uma API seja considerada tecnicamente RESTful, porém, apesar de nesse texto nenhum protocolo ser especificado, atualmente esse termo é usado de maneira muito imprecisa, de modo que normalmente se refere a uma API baseada em HTTP, normalmente usando JSON como formato de dados nos corpos de request e response.

Como já vimos, o REST define 6 princípios para que uma API seja dita, de fato, RESTful, s houver a quebra de qualquer um desses princípios (Exceto o 6º) a API não pode ser dita estritamente RESTful, são elas:

1. **Interface Uniforme**: Diz respeito a padronização da interface da API, seguindo algumas premissas e metodologias, sendo *baseada em recursos*, cada recurso representado por uma URI (Podendo mais de uma URI se referir ao mesmo recurso) e sendo *manipulados na forma de representações* dos mesmos com *mensagens auto descritivas* que contém individualmente toda a informação necessária para a manipulação do recurso, sendo trocadas entre servidor e cliente e incluindo alguma implementação de HATEOAS.
2. **Sem estado**: A segunda premissa é que o estado da aplicação não é mantido no servidor, isto é, os dados necessários para que o servidor entenda e responda uma requisição estão todos contidos na própria requisição, seja na forma de um body, nos headers, nos query parameters ou na própria URI
3. **Cacheável:** Dizer que as API RESTful são cacheáveis, significa dizer, que, de forma implícita ou explícita o servidor deixa claro se cada resposta enviada pode ou não ser armazenada em cache, evitando conexões desnecessárias e também o uso erróneo de dados desatualizados.
4. **Cliente Servidor**: A quarta guideline do REST é simplesmente uma definição do tipo de sistema que pode ser considerados RESTful: Aqueles que possuem uma estrutura cliente servidor, com clientes estruturalmente separados dos servidores.
5. **Sistemas em Camadas**: Segundo  as diretrizes, um sistema RESTful deve ser dividido em camadas isoladas, de modo que o cliente não consegue distinguir se está conectado diretamente com o servidor, a um proxy ou a qualquer outro elemento da infraestrutura
6. **Código a demanda**: O sexto princípio REST e o único opcional, code-on-demand refere-se a possibilidade de o servidor extender a funcionalidade do cliente utilizando lógica, compartilhando, por exemplo, snippets de código.


Essas 6 restrições são suficientes para enquadrar qualquer API que as siga como uma API RESTful, há porém uma série de convenções e boas práticas que podem melhorar muito a estrutura da sua API e que portanto devem ser seguidas:

1. Use os métodos HTTP para fazer com que cada request tenha um sentido compreensível pelo usuário, cada método tem uma ação e significado específico, siga essa convenção
2. Designe os recursos através de URIs que façam sentido lógico, seguindo convenções como o uso de substantivos no plural ao invés de verbos, o uso dos níveis do URI para representar a hierarquia entre os recursos e URLs que não sejam longos de mais, tudo isso torna a requisição mais fácil de processar, pelo servidor, pelo cliente, e pelo humano que gerencia ambos
3. Use status HTTP para indicar o resultado das interações de forma simples e objetiva, facilmente compreensível.
4. A menos que seja realmente impossível, use JSON
5. Por facilidade, quando estiver começando, crie recursos granulares e pequenos que refletem o domínio da aplicação, depois se tornará mais fácil agregá-los para reduzir a fragmentação

Um parêntese importante refere-se aos métodos denominados "Safe methods" pela especificação do protocolo HTTP, sendo eles os métodos `GET`, `HEAD`, `OPTIONS` e `TRACE`, ser métodos seguros significa que eles não devem modificar de nenhuma forma os recursos e isso deve ser tido como premissa ao construir uma API.

As boas práticas de desenvolvimento de APIs podem ser divididas em 7 tópicos para o desenvolvimento de uma ótima API, são eles:

1. **Design da URL**: Criar estruturas URL consistentes, legíveis e escaláveis
2. **Design das Representações**: Lidar e representar satisfatoriamente as representações dos recursos da aplicação trabalhando bem com as nuances do design de payloads
3. **Design das Requests**: Trabalhar consistentemente na utilização estruturada de métodos HTTP, query parameters e manipulação das coleções
4. **Design das Responses**: Utilizar de maneira correta e consistente com os comportamentos síncronos e assíncronos, com os HTTP status codes manipulação de erros e cache.
5. **Negociação dos Media Types**: Envolve a utilização de tipos de mídia padrão como `Accept: application/json` e outros media types bem como operações de bulk
6. **Design as relações**: Definir satisfatoriamente a relação entre os recursos e exibir de maneira intuitiva essa relação nas URIs
7. **Design da segurança**: Garantir a segurança e integridade da API, incluindo autenticação, autorização e encriptação de dados

Um "oitavo pilar" seria o pilar de documentação, que envolve todos os outros pilares e consiste em documentar e descrever bem a estrutura da API e seus requisitos e padrões seguindo padrões como o Swagger (OpenAPI).

Na época do "Avento da IA", tem se tornado cada vez mais importante desenvolver APIs tendo em mente essas ferramentas, que em geral usam APIs de 3 maneiras: 

1. ``Retrieval``: Uma LLM pode usar um endpoint de uma API para obter informações como documentos ou outros objetos para processar
2. `Actions`: Outra opção é que essa ferramentas consumam endpoints de API para realizar ações como criar um registro num banco de dados
3. `Orchestration`: Uma última opção é a utilização de APIs pelas IAs para performar ações mais complexas, unindo diferentes etapas de `Action` e `Retrieval` no mesmo objetivo macro

Sendo assim, elas não se distinguem muito de clientes comuns da API, a diferença é seu funcionamento probabilístico, que reforça a importância de não ser ambíguo, ter semânticas claras de erro e uma boa segurança, as principais boas práticas nesse sentido são:

1. Identificadores claros: Um usuário humano consegue inferir o significado de uma Id aleatório com base no contexto, as LLMs nem sempre, por isso, use identificadores claros para cada dados nos payloads de response e na documentação
2. Crie endpoints simples: Ter endpoints que performam múltiplas e complexas ações de uma única vez faz com que a IA precise inferir regras específicas, por isso, opte por endpoints simples e que fazem ações simples
3. Semântica explícita de erros: Utilize erros que incluam contexto e direcionamento suficientes para descrever bem a ação a ser tomada para resolvê-los, com status codes claros e mensagens descritivas sobre o problema que ocorreu
4. Padrões seguros e fluxo de confirmação: Para evitar erros você pode adicionar fluxos de confirmação ou um modo de dry run para endpoints que fazem ações perigosas ou potencialmente sensíveis
5. Paginação e limites fáceis de usar: Ao implementar paginação, considere o uso de um sistema simples e fácil de utilizar, com parâmetros como `limit`, `filter` e `sort`.
6. Implemente princípios de segurança e governança: 
	1. Ao trabalhar com ia, use o princípio do mínimo privilégio, dando a IA o acesso mínimo que ela precisa para realizar seu propósito e nada mais
	2. Crie requisições auditáveis, mapeando as requisições  e ações feitas pelos agentes no seu sistema
	3. Os agentes podem entrar em loop utilize headers de rate limit claros e estratégias de backoff (Criar um cool down de proteção contra múltiplas e contínuas requisições de um mesmo cliente)
	4. Evite permitir inputs de fontes desconhecidas para os agentes para evitar prompt injection nos seus modelo
7. Use instrumentos que permitam, em AI-Driven Clients, verificar os endpoints usados para cada ação, que erros bloqueiam a finalização da ação e quantas vezes os agentes fazem retry antes de cancelarem uma ação
8. Use uma documentação clara, com padrões como OpenAPI, explicitando o "O quê", "Por quê" e "quando" de cada endpoint, incluindo possíveis ordens de precedência entre as ações e tipagens e descrições claras a respeitos dos payloads de request e response, como os tipos de cada campo, se eles são opcionais ou obrigatórios
