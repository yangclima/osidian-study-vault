# Fonte 01
> https://www.cloudflare.com/en-gb/learning/ddos/glossary/hypertext-transfer-protocol-http/

O protocolo [[Como a internet funciona#HTTP|HTTP]] é a base para a World Wide Web e é usado pra carregar páginas através de links de hipertexto. Consiste num protocolo da camada de aplicação voltado para a transferência de dados entre dispositivos conectados e seu fluxo típico envolve um computador cliente fazendo uma **requisição** para um servidor.

Estas requisições são o meio através do qual aplicações, como navegadores, solicitam os dados que precisam para carregar um Website. Cada uma dessas requisições carregam uma série de informações, como:

1. A versão HTTP
2. Um URL
3. Um método HTTP
4. Os cabeçalhos da requisição HTTP
5. Um corpo opcional de requisição

O **método HTTP** é o objeto que indica a ação que uma determinada requisição HTTP está realizando contra o servidor, os mais comuns são o `GET` que indica que o cliente está solicitando que alguma informação seja enviada a ele e o `POST` que geralmente indica que o cliente está submetendo alguma informação para o servidor.

Os **cabeçalhos HTTP**, por sua vez, são basicamente uma série de informações  armazenadas no formato de pares chave-valor que são enviadas em todas as requisições HTTP e contém dados como o navegador usado na requisição, o método HTTP e outras informações fundamentais sobre a requisição.

O **corpo da requisição**, por outro lado é a parte onde estão contidas todas as informações que estão sendo submetidas pelo cliente para o servidor, por exemplo, um email e senha.

Quanto a HTTP response, ela é nada mais do que o objeto enviado pelo servidor em resposta a HTTP request contendo informações coerentes com o que foi solicitado e tipicamente contém:

1. Um Status HTTP
2. Um cabeçalho de resposta HTTP
3. Um corpo de resposta HTTP opcional

O status é basicamente um número de 3 dígitos usados para indicar o resultado da troca de informações entre cliente e servidor e segue o padrão de `1XX` para informação, `2XX` para sucesso, `3XX` para redirecionamento, `4`XX
para erro de cliente e `5XX` para erro de servidor, por exemplo, `200` equivale a um sucesso simples, `500` indica um erro de servidor, `404` indica que o recurso solicitado não existe e por aí vai...

O cabeçalho é semelhante e serve ao mesmo propósito do cabeçalho de requisição, isto é, guardar dados relevantes a respeito a resposta do servidor no forma chave valor.

# Fonte 02
> https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/Overview

Como já vimos, o protocolo HTTP é o que permite quase todo o compartilhamento de dados através da Web e se trata de um protocolo cliente-servidor, o que significa que cada transação é iniciada pelo destinatário, além disso, já vimos que ele não é orientado a conexão o que implica que não  há streaming de dados, ao invés disso, a troca de dados se dá por mensagens individuais trocadas entre cliente e servidor, sendo as mensagens enviadas pelo cliente chamadas de *requests* e as enviadas pelo servidor chamada de *responses*.

Ele foi desenvolvido em meados da década de 90 e se trata de um protocolo da camada de aplicação enviado via TCP ou uma conexão TCP criptografada com TLS e é usado para transferir documentos html, imagens, vídeos e outras mídias.

Cada requisição é enviada por uma entidade, o agente do usuário ou um proxy agindo em seu nome, na maioria dos casos, um navegador, e então processada pelo servidor que então devolve uma resposta.

Por mais que seja irrelevante na maioria dos casos, há inúmeras entidades entre o cliente de servidos, coletivamente chamadas de proxies e que performam ações como gateway e caching, além de roteadores, modens e toda uma complexa infraestrutura de rede.

Basicamente, o navegador, que age sempre como cliente ao inserirmos um URL faz uma requisição HTTP ao servidor para obter a página Web que queremos acessas sendo respondido pelo esqueleto html da página, a partir daí, ele identifica que outros recursos precisa para carregar completamente aquela página, como files ``.css`` ou ``.js`` ou imagens e vídeos e então faz outras requisições http para obter cada um desses recursos, além disso, os scripts de comportamento da página podem ainda realizar fetch de mais outros recursos e os links presentes na página funcionam como possibilidade para o usuário navegar entre páginas repetindo o processo descrito acima.

O servidor por sua vez não é necessariamente uma única máquina, podendo ser um conjunto de várias máquinas realizando balanço de carga ou outros softwares como cache, servidores de bancos de dados e etc gerando os documentos à demanda, além do que, numa mesma máquina, através do uso do HTTP/1.1 e do cabeçalho `HOST` podem ser hospedados diversos servidores compartilhando até mesmo o endereço IP.

Dentre os computadores e softwares entre o cliente e o servidor, aqueles que operar na cama de aplicação são chamados de Proxies, realizando funções como caching, logging, filtragem de dados, balanço de carga e autenticação.

Quanto aos aspectos básicos do HTTP:
1. Ele é simples, desenvolvido para que mesmo com a alta complexidade e segurança das requisições ele seja legível por humanos facilitando o seu teste e desenvolvimento.
2. Ele é extensível, os cabeçalhos HTTP permitem que através de acordos entre cliente e servidor o protocolo se comporte de maneiras específicas e eficientes desde que eles assuma uma semântica de cabeçalhos
3. Ele é sem estado, não há qualquer conexão entre duas requisições HTTP seguidas, apesar disso, usando os chamados cookies http é possível manter uma sessão entre requisições e portanto uma coerência entre diferente requisições

Como já vimos, o HTTP não é orientado a conexão e no HTTP/1.0 o que víamos é que basicamente cada requisição precisava abrir uma nova conexão TCP o que, apesar de servir ao propósito é pouco eficiente, desde lá, o HTTP/1.1 introduziu o pipelining para mitigar essa ineficiência através de conexões TCP controladas pelo Header connection das requisições, além disso, o HTTP/2.0 evoluiu ainda mais nesse sentido multiplexando as mensagens em uma única conexão ajudando a manter essa conexão aberta e mais eficiente. 

Essa densidade e confiabilidade do HTTP faz com que ele seja usado para controlar diversas funções na web, por exemplo, caching, autenticação, proxy e tunelamento e sessões.

Dessa forma o fluxo HTTP é então o seguinte:

1. Abre uma conexão TCP
2. Envia uma mensagem HTTP 
3. Lê a resposta do servidor
4. Fecha ou reusa a conexão aberta para novas conexões

A mensagem enviada é algo como:

```HTTP
GET / HTTP/1.1
Host: developer.mozilla.org
Accept-Language: fr
```

E a mensagem recebida é algo do tipo:

```HTTP
HTTP/1.1 200 OK
Date: Sat, 09 Oct 2010 14:28:02 GMT
Server: Apache
Last-Modified: Tue, 01 Dec 2009 20:18:22 GMT
ETag: "51142bc1-7449-479b075b2891b"
Accept-Ranges: bytes
Content-Length: 29769
Content-Type: text/html

<!doctype html>… (here come the 29769 bytes of the requested web page)
```

Essa mensagens, a partir do HTTP/2 deixaram de inteligíveis e passaram a ser encapsuladas em frames binários, entretanto, ao chegar no destino elas costumas ser reconstruídas em mensagens legíveis novamente.

Na mensagem enviada que demos de exemplo, temos na primeira linha o método HTTP (`GET`), que descreve a ação a ser performada e é normalmente um verbo como `GET`, `POST`, `PATCH`, `DELETE` ou um nome como `OPTIONS` ou `HEAD`, o Path (`/`) que é basicamente o caminho do recurso buscado dentro do servidor, e a versão do protocolo (`HTTP/1.1`), tudo abaixo disso são os cabeçalhos da requisição que podem ser opcionais ou obrigatórios e poderia ainda haver um corpo de requisição.

De forma similar, a resposta contém o versão do protocolo (`HTTP/1.1`), o código de status (`200`), indicando sucesso nesse caso, uma mensagem de status (`OK`), uma descrição curta e não oficial do status code,  os cabeçalhos HTTP e opcionalmente um corpo contendo o recurso solicitado.

A API (Application Programming Interface) mais comum baseada em HTTP é a chamada ``FetchAPI`` que permite que requisições sejam enviadas através do JavaScript e que substituiu a API `XMLHTTPRequest`.

# Fonte 03
> https://www.smashingmagazine.com/2021/08/http3-core-concepts-part1/

> O artigo  trata de uma discussão a respeito da história e conceitos centrais do novo `HTTP/3`, de forma muito cética e sem alarde, destacando que o aumento de performance devido a ela na verdade é muito menor do que a maioria das pessoas acha

A principal dúvida que costuma aparecer sobre o `HTTP/3` é se perguntar por que ele surgiu tão cedo com relação ao `HTTP/2`, a questão aqui é simples: ele surgiu não para consertar ou melhorar o `HTTP/2` mas para adaptá-lo.

Há alguns anos percebeu-se que o verdadeiro gargalo de eficiência da comunicação na Web não era o protocolo HTTP mas o protocolo TCP devido a algumas features que fazem parte do core desse protocolo, como o handshake que obriga que cada conexão a ser estabelecida primeiro realize uma comunicação prévia o que derruba completamente a performance ou o *head-of-line blocking* que faz com que cada compartilhamento de dados do TCP seja entendido por ele como um único arquivo o que faz com que as features de confiabilidade do TCP operem fazendo com que, mesmo compartilhando diversos arquivos simultaneamente, se os pacotes com os dados de um único arquivo forem perdidos ele atrase todos os outros arquivos.

O problema é que atualizar o protocolo TCP não é tão simples, ele não é extensível como HTTP por operar numa gama muito maior de dispositivos como roteadores, firewalls, modems, muito mais difíceis de manusear implicando sérios problemas numa possível extensão do protocolo como bloqueios de pacotes ao longo da internet.

Nesse sentido, decidiu-se que o próximo passo era então pensar num novo protocolo que resolvesse esses problemas, disso, surgiu o chamado protocolo QUIC, que roda sobre o UDP ao invés do TCP, acontece que, ao contrário do que se imaginava de início, a integração do `HTTP/2` com esse novo protocolo era muito limitada e complexa, dessa forma, o `HTTP/3` surge muito mais como uma adaptação do `HTTP/2` para o QUIC que uma evolução dele propriamente dita e as principais features "do HTTP/3" anunciadas se devem na verdade a esse protocolo subjacente.

O QUIC (Quick UDP Internet Connections) é um protocolo da camada de transporte que roda sobre o protocolo UDP (User Datagram Protocol), mas não por conta da performance como muitos pensam, idealmente ele deveria rodar diretamente sobre o IP, mas para evitar justamente os mesmos problemas que teríamos para atualizar o TCP, ele foi foi construído sobre o UDP.

O UDP é o protocolo mais básico possível e não fornece basicamente nada além do roteamento de dados entre portas da camada de aplicação, não faz handshake e nem é um protocolo confiável (Pacotes perdidos são ignorados) mas é justamente isso que o faz tão bom para algumas aplicações onde pacotes perdidos rapidamente ficam obsoletos, como streaming, videochamadas e etc.

Na verdade, sobre o UDP, o QUIC reimplementa a maioria das funcionalidade do TCP, tem verificação de confiança garantindo a chegada dos pacotes e, além disso, um handshake altamente complexo e também controle de fluxo e congestionamento, o ponto é que ele implementa essas features de uma forma muito mais inteligente e com alguns novos recursos chave.

Os principais pontos do QUIC são:

1. Ele se integra profundamente com o TLS
2. Suporta múltiplos fluxos de dados simultâneos
3. Usa ID's de Conexão
4. Usa frames

Quanto a essa integração profunda com TLS, o QUIC simplesmente não existe sem ele, ele integra o protocolo como uma parte sua e com isso não há uma versão Plain Text do QUIC como havia do HTTP/2 ou HTTP/1, a principal vantagem que isso trás é que o modelo anterior fazia com que tivéssemos 3 handshakes separados a cada conexão, um do TCP, um TLS e um do HTTP, agora, temos o handshake do QUIC integrado com o do TLS num só, de modo que os parâmetros de conexão são negociados juntamente com os de encriptação, além disso, uma parte muito maior do pacote do QUIC é criptografada com relação ao do TCP + TLS o que faz dele mais seguro, apesar de um possível overhead de encriptação (Custo de processamento). Resumindo, o QUIC é, por padrão, profundamente encriptado.

Sobre o suporte a múltiplos byte streams simultâneos o que ocorre é que desde sempre temos tentando reduzir a latência do HTTP através do reuso de conexões TCP, primeiro no HTTP/1.1 que foi o primeiro a permitir a transferência de múltiplos arquivos através de uma mesma conexão TCP, depois, o HTTP/2 trouxe a multiplexação que permitiu que, ainda no uso de uma única conexão TCP, os pacotes não precisasse ser enviados na ordem de um arquivo por vez, o problema é que ainda assim, quem controla tudo é o TCP e ele não sabe que está transmitindo múltiplos arquivos, ele enxerga tudo como um fluxo único e se um pacote for perdido todos os pacotes subsequentes, independente do arquivo ao qual pertencem terá de esperar pela recuperação do pacote, a diferença agora com o QUIC é que ele entende que está transmitindo múltiplos arquivos paralelamente e então, se um pacote for perdido ele só interrompe o stream de um file, o que acaba com o chamado *Head-of-line Blocking*.

Os IDs de conexão são outra feature interessante do QUIC, basicamente, usando o TCP, identificamos cada conexão por 4 números: O IP e a porta do servidor e o IP e a porta do cliente, se qualquer um desses números muda, a conexão se torna inutilizável no TCP e precisa ser reiniciada, a mudança então é que o QUIC adiciona os CID (Connection Identifiers) à equação, listas de IDs gerados aleatoriamente e negociados durante o handshake e que permitem a chamada migração de conexão, ou seja, quando, por exemplo, eu troco do WiFi para o 5g eu não preciso reestabelecer a conexão e posso continuar usando a antiga.

Por fim, o QUIC é muito flexível e pensado para evoluir, ele é encriptado o que permite evoluí-lo sem mexer nas máquinas intermediárias na infraestrutura de rede, ele não usa um conjunto padrão de headers para enviar os metadados do protocolo como o TCP e tem, ao invés uma variedade de frame que servem a diferentes funções e permite ainda negociar os parâmetros de transporte fazendo dele flexível e ultra compatível, todas essas e outras features fazem do QUIC uma grande tendência para o futuro, já que ele é muito permissivo e que ele foi pensado justamente para evoluir com o tempo

# Fonte 03
> https://www3.ntu.edu.sg/home/ehchua/programming/webprogramming/HTTP_Basics.html

O Protocolo HTTP é um protocolo assimétrico request-response client-server protocolo, provavelmente o mais utilizado em toda a internet, essa descrição significa que ao invés do servidor empurrar as informações para o cliente, o que ocorre é que o cliente puxa as informações do servidor. Algumas características importantes do HTTP são sua natureza stateless de modo que uma requisição é totalmente independente da outra e o fato de que o cliente e servidor conseguem negociar o tipo de dado transferido.

> *"O Protocolo de Transferência de Hipertexto (HTTP) é um protocolo de nível de aplicação para sistemas de informação hipermídia distribuídos e colaborativos. É um protocolo genérico e sem estado que pode ser usado para muitas tarefas além de seu uso para hipertexto, como servidores de nomes e sistemas de gerenciamento de objetos distribuídos, por meio da extensão de seus métodos de requisição, códigos de erro e cabeçalhos."* 
> **- RFC2616**

Quando você insere um URL no navegador ele transforma esse URL em um objeto de requisição e o envia para o servidor que, em resposta, retorna um objeto de resposta HTTP com o recurso solicitado ou uma mensagem de erro.

# URL e URI
Um URL (Uniform Resource Locator) é usado para identificar de forma unívoca um recurso na Web e tem a seguinte forma:

```
protocol://hostname:port/path-and-file-name
```

Formado pelas 4 partes:
- ``protocol``: O protocolo de nível de aplicação a ser usado pelo cliente e servidor
- `hostname`: O nome de domínio do servidor ou seu endereço IP
- `port`: O número da porta na qual o servidor escuta requests (Se ela não for especificada, a requisição é direcionada para a porta padrão do protocolo, e.g. `80` para o HTTP)
- `path-and-file-name`: O caminho do recurso solicitado

Não é permitido que um URL tenha caracteres especiais, mas eles podem ser passados na URL codificados usando o código hexadecimal ASCII precedido por `%`, por exemplo '~' é passado como `%7e`

O URI (Uniform Resource Identifier) é ainda mais completo que o URL e pode até mesmo localizar um fragmento dentro de um recurso:

```
http://host:port/path?request-parameters#nameAnchor
```

Os `request-parameter` são os famosos query param usado para realizar por exemplo pesquisa, paginação, restrição de resposta e ficam após o `?` em pares `chave=valor` separados por `&`, ao mesmo tempo  o `nameAnchor` é geralmente usado no controle de navegação numa página html por exemplo.

# Fluxo de Requisição
Basicamente, como mencionado, ao inserirmos um URL no navegador, ele transforma esse objeto em um objeto de requisição HTTP, algo da forma

```HTTP
GET /docs/index.html HTTP/1.1
Host: www.nowhere123.com
Accept: image/gif, image/jpeg, */*
Accept-Language: en-us
Accept-Encoding: gzip, deflate
User-Agent: Mozilla/4.0 (compatible; MSIE 6.0; Windows NT 5.1)
(blank line)
```

Ao receber esse objeto, o servidor então realiza uma das seguintes ações:
1. Processa o objeto  de requisição e o mapeia para um arquivo presente em um diretório e o retorna
2. Processa a request e a mapeia para um programa ou função específica presente no servidor e retorna sua saída
3. Processa a request, detecta alguma falha interna ou na requisição e retorna uma resposta de erro

Um exemplo de resposta é:

```HTTP
HTTP/1.1 200 OK
Date: Sun, 18 Oct 2009 08:56:53 GMT
Server: Apache/2.2.14 (Win32)
Last-Modified: Sat, 20 Nov 2004 07:16:26 GMT
ETag: "10000000565a5-2c-3e94b66c2e680"
Accept-Ranges: bytes
Content-Length: 44
Connection: close
Content-Type: text/html
X-Pad: avoid browser bug
  
<html><body><h1>It works!</h1></body></html>
```

Um fator interessante é o header de resposta `Content-Type` que indica o tipo de conteúdo que a resposta do servidor carrega, por exemplo, `text/html` no exemplo acima.

# HTTP Sobre o TCP/IP
O HTTP é um protocolo da camada de aplicação e até sua versão 2 ele roda sobre o protocolo TCP/IP, sendo o TCP um protocolo da camada de transporte e IP um protocolo da camada IP.

Como já vimos, o protocolo IP tem a responsabilidade de rotear pacotes entre duas máquinas na rede, cada uma representada por um endereço IP, além disso, como seria muito difícil memorizar os números IPs mesmo na sua forma quad-dotted (IPv4) e ainda mais o formato IPv6 atua quase sempre o DNS, protocolo da camada de aplicação responsável por realizar a tradução de nomes de domínio para endereços IP através de Lookup tables distribuídas. Um endereço IP especial é o ``127.0.0.1`` equivalente ao nome de domínio `localhost` usados para testes de loopback local.

Por outro lado, o TCP é um protocolo da camada de transporte que é responsável pela entrega de pacotes e multiplexação das transferências para a camada de aplicação, trata-se de um protocolo confiável que garante a entrega dos pacotes utilizando confirmações de recebimento com cada pacote recebendo um número de identificação. A multiplexação do TCP consegue distribuir dados entre 65536 portas para cada IP, sendo as primeiras 1024 (0 a 1023) reservadas para os protocolos mais comuns e o restante sendo livre para uso. 

Desse modo, resumidamente, para se comunicar usando HTTP você precisa de uma hostname e uma porta, ou seja, um socket.

# Anatomia da Request e Response
Uma mensagem HTTP básica consiste num header de mensagem e um body de mensagem opcional separados por um linha em branco.

No caso da request, a primeira linha é chamada de *request line* e tem a seguinte forma:

```HTTP
METHOD request-URI HTTP/version
```

1. ``METHOD``: (GET, POST, PUT, PATCH, DELETE, OPTIONS...) Especifica a ação que está tentando executar contra o recurso
2. `request-URI`: (/users, /time-entries, /main.js) Especifica o recurso alvo da requisição
3. `HTTP/version`: (HTTP/1.0, HTTP/1.1, HTTP/2, HTTP/3) Especifica a versão do HTTP a ser usada na requisição

Em seguida temos os headers da request, sendo basicamente pares chave valor. Se o header tiver mais de um valor eles são separados por vírgulas:

```HTTP
header-name: value1, value2, ...
```

Por exemplo:

```HTTP
POST /users HTTP/3.0
Host: api.yanlima.com
Content-Type: application/json

{
  "username": "yangclima",
  "email": "yangclima@gmail.com",
  "password": "12345678",
}
```

O formato da resposta HTTP é similar, chamamos a primeira linha de *Status Line* e ela possui o seguinte formato:

```HTTP
HTTP/version status-code reason-phrase
```

1. ``HTTP/version``: A versão do protocolo
2. `status-code`: Um código numérico de 3 dígitos gerado pelo servidor que indica o resultado da requisição
3. `reason-phrase`: Um curto resumo do significado do status code

A response também possui headers que mostrar algumas informações úteis sobre a resposta e tem a mesma forma dos da requisição:

```HTTP
header-name: value1, value2, ...
```

Por exemplo:

```HTTP
HTTP/3.0 201 Created
Date: Mon, 09 Jun xxxx 00:40:25 GMT
Content-Length: 35
Content-Type: application/json

{
  "username": "yangclima",
  "email": "yangclima@gmail.com",
}
```

Os métodos HTTP são:

1. ``GET``: Usado para solicitar um recurso como uma página, uma mídia ou um dado
2. ``HEAD``: Usado para solicitar ao server o cabeçalho que uma requisição GET iria obter, usado geralmente para controle de cache
3. ``POST``: Usado para submeter informações para o servidor
4. ``PUT``: Usado para atualizar um dado  ou recurso na web e se o dado não existir ele o cria
5. ``PATCH``: Usado para atualizar um recurso
6. ``DELETE``: Usado para deletar um recurso
7. ``TRACE``: Usado para solicitar ao servidor um diagnóstico das ações que ele executa
8. ``OPTIONS``: Solicita ao servidor a lista de métodos que ele suporta
9. ``CONNECT``: Frequentemente usado para estabelecer uma conexão SSL através do proxy.

Quanto os status codes eles pertencem sempre aos seguintes grupos:

1. ``1xx (Informational)``: A requisição foi recebida e o servidor continua o processo
2. ``2xx (Success):`` A requisição foi recebida, entendida, processada e respondida
3. ``3xx (Redirection):``É necessário tomar medidas adicionais para completar a requisição
4. ``4xx (Client Error):`` A request possui algum erro de sintaxe, formatação ou semântica e não foi compreendida
5. ``5xx (Server Error):`` O servidor falhou em responder uma requisição aparentemente válida

Nos protocolos HTTP/1.0 e HTTP/1.1 para que você possa manter a conexão TCP aberta ao invés de fechá-la a cada requisição você pode usar o cabeçalho 

```HTTP
Connection: Keep-Alive
```

Usando esse header, a resposta do servidor deve conter um header da seguinte forma:

```HTTP
Keep-Aline: timeout=5, max=200
```

Onde o `timeout` é o tempo em segundos que a conexão ficará aberta e `max`representa o número máximo de requisições que pode ser feita naquela conexão

No HTTP/1.1 em especial a conexão é Keep-Alive por padrão mas você pode usar o comportamento antigo usando:

```HTTP
Connection: Close
```

A partir do HTTP/1.1 o Header `Host` é obrigatório, a versão 1.1 introduziu os virtual hosts que permitiram mais de um servidor http por máquina e então as requisições http são mapeadas através desse cabeçalho.

```HTTP
Host: api.yanlima.com
```

É possível usar os headers também para gerar requisições condicionais, ou seja, que são respondidas de forma diferente de acordo com uma determinada condição, por exemplo:

1. `If-Modified-Since` 
2.  `If-Unmodified-Since`
3. `If-Match`
4. `If-None-Match`
5. `If-Range`

Por exemplo, `If-Modified-Since` é usado para que o servidor só retorne o recurso se ele foi modificado após uma determinada timestamp

Os principais headers são:

1. `Host: domain-name` Usado para especificar o host ao qual a requisição deve ser submetida
2. `Accept: mime-type-1, mime-type2_, ...` Usado para especificar um tipo específico de resposta você quer quando o servidor mantém múltiplas versões de um mesmo recurso
3. `Accept-Language: _language-1_, _language-2_, ...` Usado para especificar a linguagem quando uma página, por exemplo, tem versões em mais de uma língua
4. `Accept-Charset: Charset-1, Charset-2, ...` Para negociar o charset da resposta
5. `Accept-Encoding: encoding-method-1, encoding-method-2, ...` Usado para especificar os tipos de encoding suportados de um determinado  recurso, mais usado para files
6. `Connection: Close|Keep-Alive` Para alterar o comportamento da conexão TCP nas versões 1.1 e 1.0
7. `Referer: referer-URL` Usado para especificar a referência da requisição, por exemplo, a partir de qual página o usuário clicou no link para acessar o servidor
8. `User-Agent: browser-type` Usado para identificar o agente que está realizando a requisição, e.g. chrome, postman, insomnia
9. `Content-Length: number-of-bytes` Usado para especificar o tamanho do payload em requisições que contém body
10. `Content-Type: mime-type` - Usado para especificar o tipo de dado enviado numa requisição com body
11. `Cache-Control: no-cache|...` Usado para especificar as configurações de cache para o proxy
12. `Authorization`: Usado pelo client para fornecer credenciais de acesso
13. `Cookie: cookie-1=value-1, cookie-2_=value-2_, ...` Usado para retornar para o server cookies previamente definidos por ele


