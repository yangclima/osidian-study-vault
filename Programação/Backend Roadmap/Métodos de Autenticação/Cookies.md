Um `cookie`, também chamado de `web cookie` ou `browser cookie` é um pequeno arquivo de texto que o servidor envia ao navegador do usuário, de modo que o navegador pode armazenar cookies, criar novos cookies, modificar cookies existentes e enviá-los de volta ao servidor em requisições posteriores, permitindo que aplicações web armazenem quantidades limitadas de dados e se recordem do seu estado, estendendo as capacidades do [[O que é HTTP|HTTP]] que, por padrão, é stateless.

O conteúdo dos cookies normalmente é usado pelos servidores para verificar se diferentes requisições são provenientes do mesmo usuário, adequando as suas respostas a essas requisições a depender do resultado da verificação, um fluxo comum, por exemplo, é:

1. O usuário envia suas credenciais de login para o servidor, por exemplo, ao submeter um formulário
2. Se as credenciais estiverem corretas o server atualiza a UI para simbolizar que o usuário está logado e responde com um cookie contendo um `session ID` que armazena o seu status de autenticação no navegador
3. Posteriormente, quando uma nova requisição é feita, o navegador envia junto o cookie que contém o `session ID`  indicando que ele ainda considera o usuário como logado
4. Quando o recebe, o servidor checa o `session ID` e, se ele ainda for válido, ele permite o acesso do usuário ao recurso ou página solicitado, caso contrário, ele nega

Esses tokens são usados, em especial, para os seguintes 3 propósitos: **gestão de sessões** (Status de autenticação, conteúdos de carrinhos de compra e etc.), **personalização** (Especificação e configurações do usuário) e **tracking** (Armazenamento e análise do comportamento do cliente).

No princípio, esse cookies eram usados ainda como uma forma de armazenamento, antes do surgimento da `Web Storage API` e do `IndexedDB`, apesar disso, são limitados com relação ao tamanho (Normalmente 4kB por cookie) e são enviados em todas as requisições, podendo prejudicar o desempenho, sobretudo em redes lentas.

Após receber uma requisição, um servidor pode enviar um ou mais headers `Set-Cookie` na resposta, cada um dos quais, irá criar ou modificar o valor de um cookie, o que é configurado através de pares nome-valor, seguindo:

```HTTP
HTTP/2.0 200 OK
Content-Type: application/json
Set-Cookie: <cookie1_name>=<cookie1_value>
[...]
Set-Cookie: <cookieN_name>=<cookieN_value>
```

quando uma nova requisição é feita, o navegador geralmente envia os cookies previamente armazenados pelo servidor atual, utilizando um header `Cookie`:

```HTTP
GET /sample_page.html HTTP/2.0
Host: www.example.org
Cookie: <cookie1_name>=<cookie1_value>; [...]; <cookieN_name>=<cookieN_value>
```

Opcionalmente, ao definir um cookie, o servidor pode também definir uma data/hora para expiração desse cookie (Atributo `Expires`) ou uma idade máxima para ele em segundos (Atributo `Max-Age`):

```HTTP
Set-Cookie: <name>=<value>; Expires=Thu, 31 Oct 2021 07:28:00 GMT;
```

```HTTP
Set-Cookie: <name>=<value>; Max-Age=2592000;
```

Um fato notável é que a data do `Expires` é relativa ao cliente onde se encontra o cookie, podendo gerar erros e diferir da data do servidor, por isso, é mais recomendado utilizar o atributo ``Max-Age``.

Cookies sem nenhum desses atributos de life-time são deletados ao fim da sessão, mas essa sessão é definida pelo navegador e como alguns deles usam um espécie de recuperação de sessão os tokes sem `Expiration` ou `MAx-Age` podem durar para sempre. 

No cenário da utilização de cookies para a autenticação um ataque comum é o chamado **ataque de fixação de sessão** onde scripts ou aplicações de terceiros são capazes de reusar uma sessão de usuário, para evitar isso, o seu site deve sempre recriar e reenviar cookies mesmo que um válido já exista.

Para remover imediatamente um cookie, usamos:

```HTTP
Set-Cookie: <name>=<value>; Max-Age=0
```

Ou, para remover todos os cookies associados a um determinado domínio, usamos:

```HTTP
Clear-Site-Data: "cookies"
```

Para criar ou modificar o valor dos tokens no JavaScript, podemos seguir:

```JS
document.cookie = "<name1>=<value1>";
```

Porém, por questões de segurança você não pode simplesmente anexar um cookie manualmente com Set-Cookie em um fetch, ao invés disso, usamos `credentials: include` e o navegador se encarrega de anexar os cookies que pertencem aquele domínio, também é possível impedir que um cookie seja acessado via JS usando o atributo `HttpOnly`

Quando você armazena informações em cookies, esse cookies são, por padrão, visíveis para e alteráveis pelo usuário final, mas os resultados de um uso permissivo como esse podem ser catastróficas e expor tanto informações do usuário quando seu servidor a ataques, felizmente, existem variadas formas de alterar esse comportamento padrão e tornar os tokens seguros.

Para impedir o acesso de pessoas ou scripts não autorizados aos nossos cookies podemos usar dois atributos: `Secure` e `HttpOnly`, o `Secure` garante que, exceto em `localhost`, o cookie só será enviado para o servidor através de uma request segura estabelecida usando o protocolo `HTTPS`, isso não impede, entretanto, que alguém como acesso ao disco rígido do usuário (Ou JavaScript se `HttpOnly` não for utilizado) leiam e modifiquem os dados do cookie, por outro lado, usar `HttpOnly` tira a possibilidade de acessar os cookies usando scripts JS no lado do cliente evitando ataques de cross-site scripting.

Em muitas aplicações, é comum utilizar identificadores opacos, que podem ser checados quanto a validade e integridade no servidor ao invés de armazenar informações sensíveis diretamente nos cookies.

É possível ainda controlar mais especificamente quando os cookies serão enviados pelo navegador usando os atributos `Domain` e `Path`: Quando configuramos um cookie com `Domain=wattconsultoria.com.br` esse cookie será enviado em requisições para esse domínio e todos os seus subdomínios, como `dashboard.wattconsultoria.com.br` enquanto, se essa configuração não for feita, o cookie será enviado somente para o domínio que enviou a response que o criou mas não para os seus subdomínios, além disso, `Path` pode ser usado para controlar para que URL paths os cookies serão enviados, por exemplo, com `Path=/docs`, os cookies serão enviados em requisições com paths como `/docs/api` e `/docs/api/http`  mas não em requests para os paths como `/api/docs`, esse atributo, no entanto, não deve ser encarado como um recurso de segurança, mas uma forma de controlar diferentes cookies para diferentes partes de uma aplicação web.

Um outro atributo importante é o atributo `SameSite`, que controla se e quando os cookies são anexados nas chamadas requisições cross-site, requisições feitas a partir de um site mas tendo como destino outro, trata-se de mais uma opção para garantir a segurança e privacidade do usuário, aceitando como valor `Strict`, `Lax` e `None`. `SameSite=Strict` faz com que os cookies sejam enviados apenas em requisições feitas do e para o mesmo domínio que os criou, `SameSite=Lax` é similar, porém, também anexa os cookies quando o user está navegando em direção ao site que criou os cookies, por fim, `SameSite=None` inclui os cookies independente da origem da requisição, se nenhum valor for especificado, por padrão, o valor é `Lax`.

O mecanismo de cookie, por padrão, não permite garantir com 100% de certeza que um cookie vem de uma origem segura ou mesmo identificar a sua origem, para resolver isso, foram criados os chamados ``cookie prefixes``, prefixos definidos e que impõem determinadas regras aos atributos dos cookies que devem ser respeitados no navegador do cliente, por exemplo, se o nome de um cookie inicia com `__Host-` ele só pode ser definido com os atributos `Secure`, sem o atributo `Domain` e com `Path=/`. Os valores de prefixos são:

| **Prefixo**    | **O que o navegador exige para aceitar o cookie?**                                                                            | **Objetivo Principal**                                                                                                                                 |
| -------------- | ----------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `__Secure-`    | Deve ser enviado **apenas via HTTPS** (atributo `Secure`).                                                                    | Garante que o cookie nunca trafegue em canais não criptografados (HTTP).                                                                               |
| `__Host-`      | • Deve ser HTTPS (`Secure`).<br>• **Não pode** ter o atributo `Domain` (fica restrito ao host exato).<br>• Deve ter `Path=/`. | **Isola o cookie.** Impede que subdomínios criem, leiam ou sobrescrevam esse cookie. Ele pertence apenas e exclusivamente ao servidor que o criou.     |
| `__Http-`      | • Deve ser HTTPS (`Secure`).<br>• Deve ter o atributo `HttpOnly`.                                                             | Garante que o cookie **só veio do servidor** (via cabeçalho `Set-Cookie`) e que nenhum script em JavaScript malicioso (XSS) pode lê-lo ou modificá-lo. |
| `__Host-Http-` | União de todas as regras anteriores (`Secure` + `HttpOnly` + Sem `Domain` + `Path=/`).                                        | O nível máximo de segurança. O cookie fica isolado no servidor exato e totalmente invisível para o JavaScript.                                         |

Se um cookie cujo nome segue um desses prefixos tentar ser setado com configurações que vão contra as configurações do  prefixo específico ele é automaticamente rejeitado pelo navegador.

O principal uso dos cookies é no fluxo `stateful` chamado `session based auth`, ocorrendo da seguinte forma:

1. O usuário tentar fazer login enviando suas credenciais
2. O server valida as credenciais e cria um objeto de sessão em sua base de dados, retornando um resposta que seta um cookie no lado do cliente com o id de sessão
3. Nas próximas requisições, o cookie é anexado e o server então valida a validade da sessão utilizando o session id do cookie e autoriza os acesso ou identificação do usuário
4. Retorna a resposta à requisição


Um exemplo extremamente simples  e fictício  de fluxo de autenticação baseado em cookies com `README.md` descritivo e comentários explicando algumas coisas no seguinte repositório do GitHub: https://github.com/yangclima/cookie_based_auth