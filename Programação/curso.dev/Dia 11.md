O Dia 11 aborda um tema importantíssimo que envolve os bastidores do processo de disponibilizar a nossa aplicação por meio de um domínio, o DNS.
# DNS: Nível 1
O DNS ou *Domain Name System* é o responsável por podermos acessar os nossos sites favoritos através de uma URL simpática e intuitiva como `yanlima.com`,  ao invés de precisar de algo nada atrativo como `76.76.21.93` para chegar na aplicação que queremos, a verdade é que os **domínios são uma mentira**, são apenas apelidos que damos para endereços IP que fazem parte do [[Dia 4#IP|Protocolo IP]] e, por sua vez, realmente funcionam como endereços, identificando de maneira unívoca um ponto de conexão na internet. 

Na prática, o que acontece é que, ao digitar um endereço de domínio na barra de busca do navegador, o nosso computador irá enviar uma requisição ao servidor DNS, que por meio de uma complexa cadeia de ações irá identificar para que endereço IP o nosso endereço de domínio está apontando, devolvendo essa informação para o nosso computador que agora, sabendo qual o endereço IP correto, irá enviar a requisição para ele. 
# DNS: Nível 2
Lendo o texto acima, tudo parece muito simples, e não há nada equivocado nele, o único problema é que ele simplifica alguns processos, abstrai, por motivos de simplicidade, pois o que de fato ocorre é o que veremos agora.
## Os tipos de servidores DNS
No nível 1, nos referimos a O servidor DNS, a verdade é que existem inúmeros servidores DNS, divididos em  4 tipos:
### DNS Resolver ou Recursor
Para entender cada tipo de servidor DNS e o seu papel nessa cadeia, nós utilizaremos como analogia uma biblioteca, nesse caso, o DNS Resolver seria como o bibliotecário, é a ele que recorremos quando precisamos encontrar um livro. Na prática, quando digitamos um domínio no nosso navegador e ele não conhece aquele domínio, ele então envia uma requisição para o DNS Resolver, que normalmente é o seu ISP (*Internet Service Provider*), que será responsável por encontrar a resposta para a sua pesquisa e te devolver.
### Root nameserver
O root nameserver seria como um índice na biblioteca que aponta para um conjunto de estantes, é a ele que o "bibliotecário" recorre primeiro, ou seja, o DNS Resolver, uma vez que não conhece o domínio solicitado, faz uma requisição ao Root nameserver, que apontará em que "estante" está o livro procurado. Existem 13 Root nameservers, cada um designado por uma letra de A a M, ao redor do mundo, vale a pena frisar que um root nameserver é toda uma infraestrutura de vários servidores e não um único servidor.
### Top Level Domain nameserver
Na nossa analogia, o Top Level Domain ou TLD nameserver seria então a estante para a qual o índice apontou, o "bibliotecário" então checa a estante, ou seja, o Resolver solicita ao TLD pelo domínio em questão e ele responde com um "livro" específico. O TLD de um domínio como "example.com" seria o TLD "com".
### Authoritative nameserver
Eis então o nosso livro e ele é um dicionário! Nele está contida a informação que buscamos esse tempo todo, é ele que responde o Resolver com, finalmente, algo concreto, o endereço IP que buscamos até agora, no fim das contas, apenas ele, tem a informação de verdade para transformar um domínio em seu respectivo IP.

![[Pasted image 20250418225517.png|center]]
# Pesquisa DNS em etapas
1. O usuário pesquisa um endereço de domínio no navegador e o navegador então, verifica se possui em seu cache o endereço solicitado, caso não possua, ele verifica no cache do sistema operacional, caso ele também não conheça o navegador envia uma request para o DNS resolver.
2. O Resolver então verifica em seu cache e não encontrando, envia uma request para o root nameserver 
3. O root nameserver também verificará em seu cache e caso não ache, devolverá o endereço de um TLD nameserver específico
4. O resolver então envia uma requisição para o endereço do TLD nameserver específico
5. O TLD nameserver não encontrando em seu cache o domínio, retornará então o endereço de um Authoritative nameserver
6. O Resolver então envia uma requisição do domínio buscado para este Authoritative nameserver
7. O nameserver então verifica a sua base de dados e retorna o endereço IP associado
8. O resolver, na última etapa, devolve o endereço IP ao navegador
9. O navegador então solicita o recurso vinculado usando o endereço IP
10. E por último o servidor vinculado ao endereço IP devolve o recurso ao navegador