O dia 16 foi repleto de conhecimento, os principais temas abordados foram: Tipos de [[Dia 15#Testes Automatizados|testes]], API's e o funcionamento do [[Dia 4#HTTP|protocolo HTTP]].

> Nada é mágico, dê a cara a tapa e busque entender como as coisas funcionam de verdade.
# Tipos de testes
Existem três principais tipos de teste: teste de Unidade, teste de Integração e test end-to-end, e cada um deles pretender testar um escopo diferente da nossa aplicação: o unitário pretender testar um unidade, uma função, uma classe, ele costuma levar em consideração não a proposta mas a própria implementação, já o teste de integração pretender testar como as unidades trabalham juntas, como elas se encaixam uma na outra e costumam se basear na proposta, ou seja, usar como parâmetro aquilo que sua aplicação deveria fazer, o E2E, por sua vez é um nível acima e pretender testar o software o mais próximo possível da perspectiva do usuário, simulando até mesmo a interface gráfica.

O ponto é: cada nível de teste é mais caro que o outro, Unitário < De integração < E2E, então durante muito tempo, se defendeu construir os testes com base numa teoria quase intocável, a "Pirâmide de Testes", porém, debates mais recentes trouxeram novos ponto de vista para essa discussão, a pirâmide é fruto de um tempo onde o poder de processamento dos computadores era muito mais limitado o que criava um abismo enorme entre o tempo que um teste unitário e um teste de integração levava, o que tem mudado ao longo do tempo, o ponto é que, logicamente pensando, para um teste de integração passar, obrigatoriamente todos os testes unitários tem que funcionar também, então por que não realizar apenas testes de integração? O grande problema é que os testes unitários permitem testar ao extremo cada unidade e garantir que ela funciona como esperado, o que não é o caso para os testes de integração, dessa forma, para sistemas que precisam de altíssima confiabilidade 100% do tempo, os testes unitários devem sempre existir, porém, para outros tipos de software, que não lidarem com nada específico demais, essa se torna uma discussão

> Testar o que os clientes de fato vão usar  *versus* testar detalhes de abstração interna.

# Application Programming Interface
Para começar essa definição, podemos começar entendendo o que é um interface: Interface é tudo aquilo que você interage desde que não esteja mexendo em detalhes da implementação interna, um tipo de abstração. Uma GUI (Graphic User Interface) ou TUI (Text User Interface) são interface amigáveis a nós humanos, onde coisas como layout, design, exibição realmente importam, nós somos o público-alvo dessas interfaces, e toda interface tem seu público-alvo, sendo assim, uma API pode ser pensada como informação pura estruturada, sem layout, design e nada do tipo, sendo assim, API é a interface que tem como público-alvo, as máquinas.

# Usando o protocolo HTTP
Na internet, quase toda request e toda response é transmitida através do protocolo HTTP, e não há nada de mágico me como as coisas acontecem por aqui.
## Endpoint
Um endpoint é basicamente o ponto final de uma request, ou seja, basicamente qualquer endereço na internet é um endpoint, porém, costumamos as nos referir a endpoints como sendo rotas de uma API. 
## Criando um endpoint
No nosso projeto, usando [[Dia 3#Next.js|Next.js]], podemos criar facilmente um endpoint de uma API usando algo como: 
```javascript
// pages/api/endpoint/index.js

function endpoint (req, res) {
  res.status(200).send({"chave": "valor"})
}
```
Como aprendemos na última aula, podemos fazer um teste de integração para esse endpoint:
```javascript
test("GET to /api/endpoint should return 200", async () => {
  const response = await fetch("http://url/api/endpoint")
  expect(response.status).toBe(200)
})
```
# curl
O curl, que vem de *client url* é uma forma fazer requisições para endpoints diversos espalhados pela internet através da CLI, sua sintaxe é simples:
```bash
curl <URL>
```
Além disso, podemos usar as flags:
- `--verbose` para ver todos os detalhes da requisição e da resposta
- `--header` para adicionar um cabeçalho à requisição
- `--insecure` para fazer requisições https sem exigir certificado

O curl pode nos ajudar a responder uma pergunta: Como servidores como o da Vercel conseguem hospedar diversos sites e aplicações no mesmo IP e consegue entender qual o site buscado quando o DNS é resolvido? A resposta é que na requisição para o IP, passamos no cabeçalho a chave 'Host' com o valor do domínio que queremos acessar.  
# Versionamento de API
Durante a evolução do projeto de uma aplicação, as mudanças e features que surgem fazem com que, algumas vezes, precisemos adaptar as respostas dos endpoints da nossa API,o que não tem problema nenhum, desde que seja através de non-breaking changes, mudanças que não irão quebrar qualquer implementação externa da API, o grande problema é quando se faz necessário fazer mudanças que são capazes de quebrar essas implementações, casa essas breaking changes sejam inevitáveis, é essencial que o projeto tenha sido pensado desde o início para dar suporte a algum tipo de versionamento de API.
## URI Path versioning
Path versioning é a maneira mais simples e intuitiva de versionar a sua API, esse tipo de versionamento é dado através dos caminhos, da sua API, a primeira versão seria algo como `api/v1/endpoint` e a segunda algo como `api/v2/endpoint`.
## Header versioning
É um tipo de versionamento mais avançado que consiste em passar no cabeçalho da requisição uma chave como `acepts-version` com o valor descrevendo a versão desejada da API. 