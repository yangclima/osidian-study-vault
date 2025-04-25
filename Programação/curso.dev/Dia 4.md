No dia 4, entendemos o que são e quais os principais protocolos da web, bem como algumas noções de roteamento e inicialização de servidor com [[Dia 3#Next.js|next.js]] e criação de componentes com [[Dia 3#React|react]] e a trabalhar com algumas funcionalidades do nosso [[Dia 2#Ambiente de Desenvolvimento|ambiente de desenvolvimento]].
# Protocolos
Protocolos são como acordos que definem regras e diretrizes comuns a duas partes que pretendem se comunicar, por exemplo, um cliente que pretende receber um arquivo de um servidor, algo parecido com a bincadeira telefone sem fio. Os principais protocolos da web são:
## HTTP
O HTTP ou *Hypertext Transfer Protocol* é um protocolo web utilizado na transferência de Hipertexto, ou seja, arquivos que podem possuir referências para outros arquivos.
## FTP
O FTP ou *File Transfer Protocol* é um protocolo voltado a transferência de arquivos via internet.
## SMTP
O SMTP ou *Simple Mail Transfer Protocol* é um protocolo voltado a transferência de mensagens, emails.
## TCP
O TCP ou *Transfer Control Protocol* é o protocolo de transferência de dados através da internet, é sobre ele que são construídos todos os protocolos acima. Um ponto interessante do TCP é que ele possui um fator de redundância para impedir a perda de dados na transferência, porém, esse fator tem um custo: Uma perda razoável na sua eficiência (velocidade).
## UDP
O UDP ou *User Datagram Protocol* é uma alternativa ao TCP que não possui o fator de redundância, permitindo uma perda razoável de eficiência a depender da conexão e latência, apesar disso, é melhor que o TCP em conexões sensíveis ao tempo, como aplicações que envolvem VoIP ou Videoconferência.
## IP 
O IP ou *Internet Protocol* é o protocolo responsável por qualquer conexão entre dois dispositivos na internet e sua identificação através do seu endereço IP.
# Servidor Local Next
para inicializar um servidor local [[Dia 3#Next.js|Next.j]] e servir as nossas páginas e arquivos localmente nós rodamos o comando `next dev`, porém, a instalação direta do next (globalmente) não é muito comum, então precisamos fazer isso através do [[Dia 3#Node Package Manager (npm)|npm]], adicionando no nosso arquivo `package.json`, no valor relacionado aos "`Scripts`" a linha:
```json
"dev": "next dev",
```
A partir daí podemos iniciar o servidor a partir do comando
```bash
npm run dev
```
# Routing no Next.js
O roteamento no Next.js é muito simples e intuitivo e é chamado de *file-based routing* (Esse sistema é baseado no roteamento de páginas PHP com Apache server) e pode ser feito através de um dos dois diretórios, criando-os na raiz do projeto: O diretório `app` ou o diretório `pages`. O diretório `pages` é o original do Next.js, qualquer arquivo `.js` nesse diretório será interpretado como uma rota pública na sua aplicação, e o arquivo `index.js`, por motivos históricos, é interpretado como a rota raiz (Ou rota padrão) da sua aplicação, ou seja, algo como `site.com/` enquanto um arquivo `home.js` seria interpretado como uma rota `site.com/home`, cada arquivo, por sua vez, deve ser um componente react.
# Criando componentes React
Dentro de um arquivo JavaScript, e. g. `index.js`, podemos criar um componente react, e é isso que o Next.js está buscando no diretório `Pages`. Para criar um componente usamos uma função no JavaScript que deve iniciar em letra maiúscula, por convenção, e pode exportar componentes `html` normalmente, veja:
```jsx
function Home(){
    return {
        <h1> Hello world! </h1>
    }
}
```
Como um arquivo `.js` pode conter diversas funções, pra especificar para o next que aquela nossa função é o componente que ele deve renderizar, ao final do arquivo devemos definir essa função como nossa exportação padrão:
```JavaScript
export default NomeDaFunção;
```
# Objetivos
Para o projeto final do curso os objetivos principais são:
- Usar ferramentas para chegar num resultado
- Gerar impacto em alguém
- Tornar o processo prazeroso