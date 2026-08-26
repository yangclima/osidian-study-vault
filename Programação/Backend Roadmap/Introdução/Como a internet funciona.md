# Fonte 01
> https://cs.fyi/guide/how-does-internet-work

Entender como a internet funciona é essencial para que, como desenvolvedor você possa aproveitar  de toda a sólida fundação e conectividade que ela oferece para construir serviços e aplicações, seguros, efetivos e escaláveis.

## Introdução  à internet
Antes de entender o que é a internet, precisamos entender o que é uma Rede, sua unidade fundamental. 

Uma rede, nada mais é que um conjunto de dispositivos conectados entre si, por exemplo, você tem uma rede em sua casa conectando seus dispositivos, seu vizinho tem uma rede conectando os dispositivos dele e o vizinho dele também, quando conectamos todas essas redes, temos a internet o que leva-nos a definição:

> A internet é uma rede de redes

A internet, como milhares de outras tecnologias que fazem parte de nossa vida moderna, surgiu como uma tecnologia militar, nesse caso desenvolvida pelo Departamento de Defesa Norte Americano no objetivo de construir uma rede decentralizada capaz de resistir a um ataque nuclear e evoluindo depois para a complexidade e confiabilidade que tem hoje.

## Como a internet funciona: Uma visão geral
No alto nível, a internet funciona conectando dispositivos e sistemas usando uma série de protocolos padronizados que definem como os dados serão compartilhados entre dispositivos e garantem que eles sejam transmitidos com segurança e confiabilidade.

O  núcleo da internet é então formado por uma rede global de roteadores, responsáveis por direcionar o tráfego de dados entre diferentes dispositivos e sistemas. 

Quando você envia dados através da internet eles são quebrados em pequenos pacotes e enviados para um roteador que examina o pacote e o direciona para o próximo roteador no caminho ate o destino, que o direciona para o próximo e para o próximo até que os pacotes alcancem o destino final.

Para garantir que os pacotes sejam enviados e recebidos corretamente, uma série de protocolos entra em ação, em especial, o protocolo IP (*Internet Protocol*) é responsável rotear e direcionar os pacotes enquanto o protocolo  TCP (*Transmission Control Protocol*)   garante que os pacotes seja transmitidos com confiança e na ordem certa.

Além desses protocolos principais, uma série de outros entra em ação para permitir a comunicação e transmissão dos dados, dentre os quais, o DNS (*Domain Name System*), HTTP (*Hyper Text Transfer Protocol*) e  SSL/TLS (*Secure Sockets Layer/Transport Layer Protocol*).

## Conceitos Básicos e Terminologia
Para entender a internet é necessária a familiaridade com alguns conceitos e terminologias, dentre os quais, os principais são:

- **Pacote:** Uma pequena unidade de dados transferida ao longo da internet
- **Roteador:** O dispositivo que direciona os pacotes entre diferentes redes
- **Endereço IP:** Um identificador único associado a cada dispositivo numa rede usado para rotear os dados
- **Nome de Domínio:** Nome inteligível usado para identificar um website
- **DNS:** Sistema utilizado para traduzir nomes de domínio em endereços IP
- **HTTP:** Protocolo usado para transmitir dados entre um cliente e um servidor
- **HTTPS:** Uma versão encriptada do HTTP que permite comunicação segura entre cliente e servidor 
- **SSL/TLS:** Protocolos usados para permitir comunicação segura na internet

## O papel dos protocolos
O papel dos protocolos na internet é extremamente crítico, são eles que garantem, como falado anteriormente, que a comunicação na internet seja feita de modo seguro e confiável, mas afinal, o que é um protocolo? Nada mais é que uma conjunto de regras e padrões que definem como a comunicação ocorre e como os dados são transferidos entre os dispositivos.

Por exemplo, o endereço IP permite a identificação unívoca dos dispositivos e o correto roteamento dos pacotes ao longo da rede, enquanto protocolos como TCP e UDP (*User Datagram Protocol*) garantem a transmissão rápida e efetiva dos pacotes e o HTTP ou SMTP são os protocolos que determinam as regras de comunicação entre cliente e servidor.

A grande vantagem da aplicação desses protocolos é que eles permitem a comunicação mesmo entre dispositivos de diferentes praticantes desde que obedeçam as regras predefinidas por estes protocolos.
## Entendendo Endereço IP e DNS
Como vimos, cada dispositivo numa rede é identificado por um endereço IP, tipicamente representado por um conjunto de números separados por pontos como $192.168.1.1$ que permitem a correta transmissão dos dados na rede, o problema é que números são difíceis de lembrar e acessar e por isso surgiram o DNS, que transforma esses números em palavras legíveis como **google.com**, de forma que, quando você acessa esse nome de domínio no seu navegador, ele faz uma requisição a um servidor DNS que encontra o endereço IP associado a esse nome de domínio e permite que você o acesse através do protocolo de comunicação adequado
## Introdução ao HTTP e HTTPS
O HTTP e HTTPS são os dois mais usados protocolos de comunicação em aplicações e serviços na internet.

Quando você visita um site seu navegador faz uma requisição HTTP para o servidor solicitando um determinado recurso, o servidor então responde essa solicitação com os dados solicitados.

Por outro lado, o HTTPS nada mais é que uma versão criptografada do HTTP que faz uso do SSL/TLS para criar uma camada a mais de segurança ajudando a proteger suas credenciais, informações de pagamento e dados pessoais.

## Construindo aplicações com TCP/IP
Os protocolos TCP/IP são os protocolos implícitos de comunicação mais utilizados na maioria dos serviços e aplicações da internet e são eles que garantem a transmissão confiável, ordenada e com checagem de erros entre aplicações rodando em diferentes dispositivos.

Associados a esses protocolos temos alguns conceitos:

- **Portas:** Portas são usada para identificar cada aplicação rodando em um mesmo dispositivo, cada aplicação associada a um único número de porta 
- **Socket:** Um socket é o conjunto de um número de porta e um endereço IP, representando um endpoint específico para a comunicação
- **Conexões:** Uma conexão é estabelecida entre dois sockets quando dois dispositivos querem se comunicar entre si, durante os estabelecimento dessa conexão, ocorre o chamado handshake onde os dispositivos negociam diversos parâmetros da comunicação que determinam como os dados serão transmitidos nessa conexão.
- **Transferência de dados:** Uma vez que a conexão está estabelecida, os dados podem ser transferidos entre os dispositivos, normalmente em segmentos pequenos, cada um contendo uma sequência numérica e uma série de outros metadados.

## Comunicação com SSL/TLS
Quando usamos SSL/TLS para prover uma conexão segura precisamos ter alguns conceitos em mente:

- Certificados: Certificados SSL/TLS são certificados usados para garantir a  confiança entre cliente e servidor, contendo informações a respeito da identidade do servidor e sendo assinadas por uma terceira parte confiável chamada Autoridade Certificadora garantindo sua autenticidade
- Handshake: Durante o processo de handshake, o servidor e o cliente negociam parâmetros de comunicação como o algoritmo de encriptação que será usado na comunicação segura.
- Encriptação: Uma vez que a comunicação segura é estabelecida, os dados são encriptados usando o algoritmo acordado e podem ser transmitidos de forma segura ao longo da internet

# Fonte 02
> https://web.stanford.edu/class/msande91si/www-spr04/readings/week1/InternetWhitepaper.htm

## Endereços IP
Como a internet é uma gigantes rede de computadores e outros dispositivos, cada computador dessa rede deve ser identificado através de um endereço, esses endereços tem o formato $nnn.nnn.nnn.nnn$  com cada conjunto $nnn$ variando no intervalo $0$-$255$ (IPv4), e se chamam endereços IP.

Quando você se conecta a um ISP (Internet Service Provider) você normalmente recebe um endereço de IP temporário fornecido dinamicamente através de um servidor DHCP (Dynamic Host Configuration Protocol) ou pode ter um endereço IP fixo no caso de estar conectado em uma LAN (Local Area Network).

## Stack de Protocolos e pacotes
Com um dispositivo já identificados na rede por um endereço IP, precisamos, para nos comunicar com um outro dispositivo de uma pilha de protocolos que permitirão a transmissão dos nosso dados, no caso da internet, essa pilha é normalmente chamada de TCP/IP já que os dois principais protocolos que a ela pertencem são os protocolos IP e TCP.

Quando enviamos um dado ao longa da internet ele passa por várias camadas desse protocolo, seguindo os seguintes passos:

1. Primeiro o pacote passa pela **camada de aplicação**, onde rodam protocolos como o HTTP, SMTP, FTP e outros, ainda nessa camada, e em qualquer outra, o pacote pode ser quebrado em pequenos chunks chamados de Pacotes.
2. Depois, o pacote segue para a camada TCP onde é assinado com um número de porta, um identificador que especifica a qual aplicação do destinatário esse pacote é direcionado
3. Em seguida, o pacote chega na camada IP, onde é assinado com o seu IP de destino, tendo agora a informação completa de destinatário,  formada pelo conjunto do número da porta + o endereço IP
4. Após isso, o pacote chega na camada de hardware, onde é transformado em sinais eletrônicos e então encaminhado para o seu ISP
5. No ISP, conectado diretamente com a internet, o pacote chega a um roteador que, baseado no IP de destino, direciona o pacote em direção ao seu destino ou ao próximo roteador
6. Quando o pacote eventualmente chega no destino final ele faz o caminho inverso, é transformado pela camada de hardware em dados novamente, a camada de IP remove dele a informação de IP de destino confirmando a chegada no local, a TCP remove a informação a respeito da porta e o direciona a aplicação correta onde a informação é finalmente remontada e processada.

<img src='ber_001.png' alt='center'>
## Infraestrutura de rede 
Agora já sabemos como os dados trafegam próximo a nós, mas a maior parte do caminho está ainda omitida, demos agora um zoom na "internet" mostrada no diagrama do tópico anterior.

Basicamente os pacotes, transformados em sinais eletrônicos, saem da sua infraestrutura local passando pelo seu modem e são direcionados a pools de conexão pertencentes a seu ISP de onde vão para os roteadores do ISP e então para o backbone da internet, pertencente ao seu provedor ou alugado por ele, uma rede enorme de roteadores que, passo a passo, deixam seus pacotes cada vez mais próximos do destino final (podemos checar isso para um pacote qualquer e acompanhar todo o seu caminho até o destino final usando o comando `tracert`).

Essa espinha dorsal da internet é feita de muitas gigantescas redes que se interconectam, chamadas de NSPs (Network Service Providers) que interagem entre si para trocar dados através de conexões com os chamados NAPs (Network Access Points) onde os dados passam de uma NSP para a outra, além disso, as NSPs também se conectam com as chamadas MAEs (Metropolitan Area Exchanges) que servem ao mesmo propósito das NAPs mas são privativas. Tanto as NAPs quanto as MAEs são chamadas de IXs (Internet Exchanges Points, conhecidos como PTT ou Pontos de Troca de Tráfego no Brasil). A NSPs de mais alto nível ainda vendem largura de banda para redes menores como ISPs.

Mas então como o pacote de fato é transmitido até o destino? Seria impossível que todos os computadores soubessem onde estão todos os outros computadores do mundo, por isso, existe uma hierarquia de roteamento, cada roteador na rede mantém tabelas com informações sobre as sub-redes que estão conectadas a ele e os endereços que elas utilizam, mas não conhecem os endereços das redes que estão acima dele, então basicamente, quando um pacote chega num roteador ele verifica o endereço IP anexado pela cada IP do computador que o enviou e verifica em sua tabela de roteamento se ele conhece aquele endereço, no caso positivo, ele envia o pacote para essa rede, no caso negativo, ele manda o pacote para uma rota padrão, isto é, o próximo roteador acima dele na hierarquia, o processo é então repetido até que o pacote chegue, no pior dos casos, até os roteadores da backbone da NSP, no roteadores com as maiores tabelas de roteamento que então começam a direcionar o pacote corretamente descendo na hierarquia de roteadores até seu destino final. 

## Nomes de Domínio e Resolução de Endereços
Vimos que as informações trafegam na rede através dos endereços IP, mas já pensou que chato seria se toda vez que precisássemos acessar um site tivéssemos que digitar o seu endereço IP no navegador? O que nos permite não precisar fazer isso é o chamado DNS (Domain Name Service), basicamente, quando digitamos um url no navegador o nosso computador acessa toda uma infraestrutura que transforma algo como `google.com` em algo como `2800:3f0:4004:814::200e`.

O DNS é uma base de dados distribuída que mantém o controle dos nomes de domínio e seus respectivos endereços IP. Seguindo uma estrutura hierárquica parecida com a dos roteadores, os servidores DNS são distribuídos com cada um contendo um subconjunto da base de dados completa de como que cada servidor, caso não tenha a informação solicitada numa requisição, a encaminha para o próximo servidor, no topo da hierarquia de DNS estão os Domain Root Servers, alguns dos maiores, mais antigos e mais comuns domínios, como `.com`, `.gov` ou `.edu`.

Sempre que uma conexão é iniciada, é especificado um servidor DNS, de modo que qualquer aplicação que necessita de resolução de nome de domínio pode operar facilmente, ou seja, quando você digita um URL no seu navegador ele primeiro resolve o nome de domínio usando o servidor DNS primário e então realiza a requisição usando o endereço IP obtido.

## Principais Protocolos
Na seção sobre a stack de protocolos vimos superficialmente os principais protocolos que permitem o funcionamento da internet, no entanto, há diversos outros protocolos que fazem parte desse sistema, alguns dos quais veremos agora:

### HTTP
Um dos mais utilizados serviços da internet é o WWW (World Wide Web), cujo funcionamento se deve, em grande parte ao HTTP (Hyper Text Transfer Protocol), um protocolo da camada de aplicação (O topo da camada TCP) usado pelos web servers e web clients para se comunicar na internet.

Dizemos que o HTTP é um protocolo baseado em texto e sem conexão, ao contrário da maioria dos outros protocolos, chamados de protocolos orientados a conexão, que mantém uma conexão aberta na internet, o HTTP não o faz,  e cada requisição carece de uma nova conexão.

Basicamente então o que ocorre quando digitamos um URL no navegador é que:

1. Se o URL possui um nome de domínio o navegador primeiro o resolve usando o DNS e obtendo o endereço IP do servidor requisitado
2. O navegador conecta com o servidor e envia a requisição HTTP através da stack de protocolos
3. O servidor web processa a requisição e verifica se a página requisitada existe, devolvendo-a em caso positivo
4. O navegador recebe a página e a conexão é fechada
5. O navegador então percorre a página verificando a disponibilidade de mídias como imagens e outros
6. Para cada mídia o navegador faz requisições HTTP adicionais
7. Quando o navegador termina de carregar todas as mídias o site é então completamente carregado na janela

### SMTP
Outro protocolo muito usado é o SMTP (Simple Mail Transfer Protocol) que é aplicado no envio de emails ao longo da internet, consistindo em um protocolo baseado em texto e orientado a conexão com cada transação seguindo mais ou menos a seguinte ordem:

1. O cliente de email estabelece uma conexão com seu servidor de email padrão, cujo IP ou nome de domínio normalmente é especificado durante a instalação do cliente
2. O servidor então envia uma mensagem inicial se identificando
3. O cliente então manda uma mensagem `HELO` que o servidor deve responder com `250 OK`
4. a depender da operação que o cliente quer realizar ele enviara através da conexão aberta os comandos voltados a essa ação
5. Essa conexão então continua até que o cliente encerre a conexão com o comando `SMTP QUIT`, respondido pelo servidor com uma mensagem de encerramento

### TCP
Abaixo da camada de aplicação fica a camada TCP, quando aplicações abrem uma conexão através da internet os dados enviados através de um protocolo de aplicação específico descem a stack de protocolos chegando na camada TCP, responsável por direcionar os dados para a aplicação correta no computador de destino e fazendo isso através dos números de porta, que podem ser entendidos como canais de comunicação separados no computador e que permitem a transação simultânea de dados entre diversas aplicações.

Basicamente, quando o TCP recebe os dados da camada de aplicação, ele os segmenta em chunks e adiciona a cada chunk um cabeçalho com informações específicas como a porta de origem e a de destino, já quando ela recebe os dados da camada de IP ela retira o cabeçalho de origem, realiza, se necessário a remontagem dos dados e os envia para a aplicação correta baseado na porta presente no cabeçalho.

Diferente do HTTP e do SMTP, o TCP não é um protocolo de texto, ele é um serviço de compartilhamento de bytes confiável e orientado a conexão, o que significa que ele primeiro estabelece uma conexão antes de enviar os dados e que possui sistema de garantia da confiabilidade da entrega realizando um aviso de entrega ao remetente sempre que um novo pacote chega e incluindo em seu cabeçalho uma soma de checagem que permite identificar erros de envio.
### IP
Ao contrário do TCP, o protocolo IP é um protocolo não confiável e sem conexão que tem como único objetivo direcionar os pacotes entre os computadores e não se preocupa se os pacotes estão em ordem, se chegaram todos ou mesmo se seguiram o mesmo caminho de modo que cada pacote IP é uma entidade individual.

A única coisa em comum entre IP e TCP é que ambos adicionam um cabeçalho com informações relevantes aos pacotes transmitidos, de modo que quando uma aplicação quer enviar dados ao longo da internet esses dados primeiro passam pela camada TCP onde são segmentados e recebem um cabeçalho e depois vão para a camada IP onde recebem outro cabeçalho e somente aí seguem seu caminho ao longo da internet.
# Fonte 3
> https://www.youtube.com/watch?v=zN8YNNHcaZc

Apesar de já entender agora no nível de software como funciona a internet, ainda há alguns princípios que precisam ser esclarecidos e olharemos então para a internet a nível de hardware entendendo um pouco melhor os periféricos usados para estabelecer uma conexão entre computadores.

Quando temos um casa ou um escritório, para que os computadores locais se comuniquem entre si tudo o que precisamos é de **Switch**, um periférico de rede cuja função principal é trocar informações localmente entre computadores que se conectam nele através de cabos de rede (CAT-5, CAT-6, CAT-7...), uma outra opção é utilizar um **Access Point** que faz exatamente a mesma função mas usando conexões sem fio, formando a unidade fundamental da internet: A rede LAN (Local Area Network).

Essa configuração entretanto ainda não é suficiente para se conectar na internet, para tal, precisamos de um intermediador, nosso segundo periférico de rede: O **roteador**, cuja função é conectar a rede LAN à outras redes LAN através da internet, dessa perspectiva, a internet nada mais é que um conjunto enorme de roteadores que direciona o tráfego de dados à demanda entre os diversos dispositivos e redes nela conectados (Vale notar que os "roteadores" que usamos em casa são, na verdade uma 3 em 1 de Roteador, Switch e Access Point).

Os roteadores usam algoritmos complexos pra formar as chamada tabelas de roteamento que permitem que eles direcionem corretamente os dados de um lado para o outro, mas então por que simplesmente não usar um único roteador central para fazer esse papel? Aqui entramos no conceito de *Single Point of Failure*, já imaginou se fosse assim e esse roteador simplesmente parasse por algum problema? A internet surgiu justamente para ser uma rede descentralizada que permanece de pé mesmo que alguns dos equipamentos que a compõe quebrem ou parem de funcionar, além disso, seria inviável a quantidade de cabos que precisaríamos se cada casa ou escritório precisasse se conectar diretamente a um grande roteador central, além disso, o roteamento descentralizado usa diversos parâmetros para realizar o roteamento garantindo que seus pacotes atravessem a rede tão rápido quanto possa, mais um vantagem do modelo descentralizado! 

Um outro fato interessante é que os próprios servidores de serviços são distribuídos ao longo do planeta, com sedes em vários locais simultaneamente utilizando *load balances* para controlar e balancear o fluxo de dados, garantindo que o delay seja tão pequeno quanto possível.

Mas e se quisermos unir várias LANs? Nesse caso, formaremos o que chamamos de WAN (Wide Area Network), permitindo que computadores de diferentes LANs se comuniquem como se estivessem no mesmo ambiente, a grande vantagem disso vem quando nos lembramos que a internet é uma área pública e por isso, tem alguns problemas de segurança acoplados fazendo que seja do interesse de uma companhia, por exemplo, manter seus ambientes conectados numa WAN evitando os perigos de cyber segurança,  a forma mais simples e barata de fazer isso é através da chamada VPN (Virtual Private Network).

Uma VPN cria um túnel seguro de conexão entre duas LANs que evita acesso externo as dados trocados através dessa conexão, e faz isso através da encriptação e encapsulamento, basicamente, antes de uma informação ser enviada ela é codificada e encapsulada e segue seu destino pelo túnel da VPN, no fim da linha, o pacote é desencapsulado e  decriptado e as informações voltam a ser legíveis, se alguém intercepta o pacote no meio do caminho ele não conseguirá fazer nada com isso, uma vez que os dados estão criptografados.

Note entretanto que apesar de a internet ser uma área pública, isso não quer dizer que seus dados estão sempre inseguros, quando trocamos informações sensíveis, usamos a chamada **End to End Encryption**, parecido com o que a VPN faz, basicamente, criptografamos os dados no cliente e decriptografamos no servidor e vice-versa, garantindo que seus dados trafeguem seguros pela rede.

Uma outra possibilidade é conectar diretamente duas LANs através da conexão entre os seus Switches, quando isso ocorre temos uma CAN (Campus Area Network), além disso, uma outra possibilidade é conectar as duas redes através de um roteador próprio, o que forma uma Private WAN, ademais, há ainda a possibilidade de comprar uma conexão dedicada na internet, o que, infelizmente, requer um grande investimento.

O último zoom que daremos para entender como a internet funciona internamente é no Provedor de Internet, os nossos ISPs, que nada mais são do que companhias que cobram pelo acesso a internet, o fato é que essas companhias seguem uma interessante hierarquia, onde no topo estão as ISPs globais que controlam o tráfego de dados entre países e continentes, seguidos por ISPs regionais que conectam cidades, estados ou mesmo países e então pelos ISPs locais, de menor porte, os servidores da maior parte dos serviços, por incrível que pareça, não se conectam somente nos provedores globais, na verdade eles se distribuem pelo mundo todo garantindo o aceso aos dados com maior confiabilidade e ainda realizam o chamado peering criando conexões locais como parceiras com os ISPs locais para garantir ainda mais rápido acesso aos dados.

