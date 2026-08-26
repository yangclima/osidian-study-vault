> https://developer.okta.com/blog/2017/06/21/what-the-heck-is-oauth

> https://www.digitalocean.com/community/tutorials/an-introduction-to-oauth-2

O OAuth é um pattern aberto de autorização, um padrão que os aplicativos podem usar para prover "acesso seguro delegado" e opera sobre [[O que é HTTP|HTTPS]] sendo então usado para autorizar dispositivos, APIs, servidores e aplicativos usando tokens de acesso ao invés de credenciais. 

Existem duas versões do OAuth o ``OAuth 1.0a`` e o ``OAuth 2.0``, completamente diferentes, sendo a versão 2.0 a mais largamente aplicada e o foco da nossa discussão inicial.

Antes do surgimento do OAuth, os sites pediam que você digitasse sua senha e usuário diretamente em um formulário deles para que, então, o sistema deles fizesse login na sua conta (como o seu Gmail) se passando por você. Essa prática ficou conhecida no mundo da tecnologia como o `password anti-pattern`.

Para criar um sistema melhor para a Web, a identidade federada foi criada para o single sign-on (SSO), nesse cenário, para autenticar-se a um aplicativo, o usuário faz uma requisição para um provedor de identidade que então cria um token assinado criptograficamente e o repassa para o aplicativo que então confia no provedor de identidade. 

Esse modelo ganhou destaque com o SAML 2.0, um padrão da OASIS lançado em 15 de março de 2005. Trata-se de uma especificação extensa, mas seus dois componentes principais são o protocolo de solicitação de autenticação (também conhecido como Web SSO) e a forma como os atributos de identidade são encapsulados e assinados — o que é chamado de *SAML assertions*.

O SAML consiste basicamente num cookie de sessão no seu navegador que te dá acesso a web apps, ele funciona bem no navegador mas é limitado quando passamos a pensar em perfis de dispositivo e ações fora de um navegador tradicional, ele fazia muito sentido quando foi lançado, depois disso, no entanto, nos dias de hoje em especial, temos diversos casos de uso muito comuns onde o SAML simplesmente não funcionaria.

O problema todo foi então resolvido pelo padrão OAuth e a autenticação delegada, ao invés de fornecer suas credenciais para um aplicativo externo, você literalmente conecta no serviço (Gmail, por exemplo) e este gera um token que dá um acesso limitado para o aplicativo usar as suas informações, seguindo o seguinte fluxo:

1. O aplicativo solicita autorização ao usuário
2. O usuário autoriza o aplicativo e fornece a comprovação
3. O aplicativo apresenta a comprovação de autorização ao servidor de autorização para obter um token
4. O token é restrito para acessar apenas o que o usuário autorizou para aquele aplicativo específico

São então os principais componentes do  OAuth: `Scopes and Consent`, `Actors`, `Clients`, `Tokens`, `Auhtorization Server` e `Flows`.

Os `Scopes` são os itens que você vê na tela quando um app te pede permissão, conjuntos de permissões solicitados pelo cliente ao pedir um token definidos pelo desenvolvedor durante a criação do app, esse é um ponto chave do OAuth, ele desacopla a decisão de políticas de autorização da aplicação, ao invés de fornecer acesso a toda a sua conta, ao fornecer um token, você especifica, ou pelo menos aceita, os escopos que a aplicação te pede e serão esses items solicitados, estritamente, os únicos que a aplicação poderá acessar.

Os atores (`Actors`) do OAuth são 4: O ``Resource Owner``, aquele que possui os dados armazenador no servidor de recursos, O ``Resource Server`` (o servidor que detém os dados que a aplicação que acessar), o ``Client`` (a aplicação que quer acesso aos dados) e o ``Authorization Server`` (O motor principal do OAuth).

Os `Clients` podem ser divididos em **clientes confidenciais**, aqueles que rodam em ambientes seguros e controlados, inacessível ao usuário final, como servidores back-end tradicionais,  e os **clientes públicos**, aqueles que rodam em ambientes expostos ou no dispositivo do próprio usuário, nesse contexto, um processo chave é o `Client Registration`, como um emplacamento do OAuth, onde você, para ser um cliente confidencial precisa conseguir uma licença para a sua aplicação.

Os `Tokens` do OAuth se referem aos tokens usados para acessar o `Resource Server`, tokens de duração curta e que não podem ser revogados, existem também o ``Refresh Token``, com duração muito maior e podendo ser revogados ocasionalmente, revogando o acesso da aplicação, o padrão OAuth não define o que são esses tokens, porém os [[JWT]] são definitivamente os mais usados para essa finalidade.

Esses `token` são obtidos através de endpoints do servidor de autorização, nesse sentido, os dois principais endpoints são o `authorize endpoint` e o `token endpoint`, o endpoint de autorização é onde você vai para obter autorização e consentimento do usuário, retornando uma concessão de autorização que diz que o usuário consentiu com ela e que é então passada para o endpoint de tokens que te fornece o ``access token`` e o ``refresh token``, você pode então usar o token de acesso para acessar as APIs e uma vez que ele expira você retorna ao endpoint de token usando o refresh token para pegar um novo token de acesso.

Chegamos no principal ponto de fricção para os desenvolvedores no OAuth: Gerenciar os refresh tokens, essa é a grande desvantagem do modelo, trata-se de um trade-off de simplicidade por segurança, você ganha a possibilidade de security features como rotação de chaves, logout simples, mas tem um modelo de implementação razoavelmente mais complexo, contudo, hoje, esse modelo de autenticação é muito maduro e provavelmente seu framework favorito de desenvolvimento já tem um toolkit disponível para facilitar as coisas.

Por segurança, os fluxos de obtenção da autorização do `Resource Owner` e de acesso aos seus recursos ocorrem em canais diferentes, para obter o consentimento do usuário, uma conexão é feita diretamente do navegador do usuário para o servidor de autorização, o que chamamos de **front channel**, uma vez concedida a autorização as conexões entre o ``Client`` e o servidor de autorização ou entre o `Client` e o servidor de recursos passa a ocorrer via requisições HTTP diretas, o que chamamos de **back channel**.

Em geral, o fluxo no front channel é algo parecido com:

1. O `Resource Owner` inicia o fluxo para delegar o acesso a um recurso protegido
2. O `Client` envia um solicitação de autorização com os `Scopes` desejados para o endpoint de autorização do `Authorization Server` via redirecionamento no navegador
3. O `Authorization Server` retorna um diálogo de consentimento perguntando ao usuário se ele deseja fornecer acesso aos escopos especificados (Claro que para isso o `Client` precisa estar logado ou então, antes do diálogo de consentimento o `Authorization Server` exibirá um diálogo de login)
4. A concessão de autorização é então passada de volta para o `Client` ainda via redirecionamento no navegador

No passo 2, a requisição de autorização se parece com:

```HTTP
GET https://accounts.google.com/o/oauth2/auth?scope=gmail.insert gmail.send
&redirect_uri=https://app.example.com/oauth2/callback
&response_type=code&client_id=812741506391
&state=af0ifjsldkj
```

Esse é um exemplo de uso da API do Gmail (Sem URL encoding para facilitar a leitura), veja todos os parâmetros usados, `scope=gmail.insert gmail.send` define quais scopes a aplicação está solicitando, `redirect_uri=https://app.example.com/oauth2/callback` fala para API para onde o usuário deve ser direcionado quando clicar em permitir (Esse URL deve ser igual ao especificado no processo de `Client Registration`), `response_type=code` especifica para a API que tipo de retorno ela deseja (Que fluxo de OAuth deve ser usado), no caso, um `Authorization Code` via navegador, `client_id=812741506391` declara o Id público do `Client` que está solicitando a permissão (Gerado no momento do `Client Registration` é ele que o google usa para exibir o nome e logo do app no diálogo de autorização) e `state=af0ifjsldkj`, que consiste num código gerado pelo `Client` no momento da solicitação e que será retornado pelo servidor de autorização para garantir que de fato se trata desse servidor retornando a concessão e não um hacker tentando se passar por ele.

Após a validação, a resposta é:

```HTTP
HTTP/1.1 302 Found
Location: https://app.example.com/oauth2/callback?
code=MsCeLvIaQm6bTrgtp7&state=af0ifjsldkj
```

O Código ``302 Found`` é quem explicita para o navegador que ele deve redirecionar para `https://app.example.com/oauth2/callback` com os params `code` que é a tal concessão de autorização, e o `state`, para confirmar a identidade do servidor de autorização.

A próxima parte do fluxo continua no milissegundo seguinte no back channel com uma requisição do `Client` para o endpoint `token` do `Autorization server` passando a concessão e também uma secret própria:

```HTTP
POST /oauth2/v3/token HTTP/1.1
Host: www.googleapis.com
Content-Type: application/x-www-form-urlencoded

code=MsCeLvIaQm6bTrgtp7&client_id=812741506391&client_secret={client_secret}&redirect_uri=https://app.example.com/oauth2/callback&grant_type=authorization_code
```

No corpo da requisição que é URL encoded `code` é a concessão de autorização, o `client_id` e `client_secret` é como um par usuário e senha do client para que ele se identifique, o `redirect_uri` serve para uma confirmação cruzada onde o servidor de autorização vai confirmar se o URL de redirecionamento é o mesmo para o qual o código foi enviado, por segurança e, por fim, `grant_type`  é quem define formalmente o fluxo de OAuth que está sendo seguido. Essa requisição é então respondida com algo como:

```JSON
{
  "access_token": "2YotnFZFEjr1zCsicMWpAA",
  "token_type": "Bearer",
  "expires_in": 3600,
  "refresh_token": "tGzv3JOkF0XG5Qx2TlKWIA"
}
```

No uso desses tokens você pode ser reativo, sempre que receber um erro de token expirado realiza uma renovação do token de acesso ou proativo, enviando periodicamente requisições de renovação. Uma vez com o token de acesso válido e não expirado, você pode acessar os recursos protegidos aos quais solicitou acesso:

```
curl -H "Authorization: Bearer 2YotnFZFEjr1zCsicMWpAA" \
  https://www.googleapis.com/gmail/v1/users/me/messages
```

A complexidade desse processo aumenta quando você passa a ter vários `Client`, dois canais e diferentes endpoints, é preciso combiná-los de modo distinto para cada use case.

Um outro fluxo de autorização é o chamado **Implicit Flow**, otimizado para clients públicos que rodam exclusivamente no navegador, como Single Page Applications (SPA),  nele, um token de acesso é retornado diretamente da solicitação de autorização, normalmente não suporta refresh tokens e assume que o `Resource Owner` e o `Client` estão no mesmo dispositivo, o problema desse fluxo é que, por ocorrer completamente no navegador, ele é mais vulnerável a ataques e brechas de segurança. Hoje, esse fluxo é considerado inseguro e deve ser evitado.

O padrão de ouro é o `Authorization Code Flow`, conhecido como 3-Legged OAuth, que faz o uso tanto do front como o do back channel, o front channel é usado para obter a concessão de autorização que é então passada pelo cliente para o servidor de autorização através do back channel para obter o token de acesso e opcionalmente o token de refresh, esse fluxo assume que a o `Client` e o `Resource Owner` estão em dispositivos distintos e é muito mais seguro, afinal, o token nunca passa por um user-agent, sendo menos vulnerável.

Um terceiro fluxo, conhecido com 2 legged OAuth, o `Client Credential Flow` é usado em cenários servidor-servidor, isto é, não há um resource owner envolvido e por isso a troca de informações é toda feita através do back channel e consiste totalmente no envio de credenciais do `Client` para obter um token de acesso, suportando chaves compartilhadas ou asserções como credenciais assinadas com chaves simétricas ou assimétricas.

Outro fluxo, é o fluxo legado chamado de `Resource Owner Password Flow`, totalmente não recomendado e que consiste basicamente em passar a sua senha e username para o `Client` e ele te retorna um token de acesso do servidor de autorização, esse método geralmente não suporta refresh tokens e assume que o `Resource Owner` e o `Public Client` estão no mesmo dispositivo.

Um fluxo adicionado mais recentemente é o chamado `Assertion Flow`, similar ao `Client Credential Flow` e permite que um `Authorization Server` confie em concessões de autorização vindo de terceiros como um (Um serviço centralizado que armazena e verifica a identidade do usuário), o servidor de autorização confia no provedor de identidade e usa a asserção para obter um token de acesso no endpoint de token, como as assertions SAML tem tempos de expiração curtos não há refresh tokens nesse fluxo e você precisa solicitar um novo token com as credenciais sempre que acaba a duração do anterior, esse fluxo é muito usado por companhias que possuem servidores legados SAML de identificação de funcionários.

Por fim, fora da especificação original do OAuth existe o `Device flow` usado em dispositivos que não contam com navegadores web, como televisores, nele, é gerado um código de usuário que deve ser resgatado usando uma URL num outro dispositivo que contenha um browser e o back channel é usado para aprovar a autorização e gerar um token de acesso e opcionalmente um refresh token, esse fluxo também é muito usado no em interfaces de linha de comando.

Além desses fluxos, existem outros, tanto que o OAuth é quase que um framework de autorização.

O OAuth, apesar dos inúmeros mecanismos, tem uma grande superfície de ataque e existem inúmeras pessoas tentando explorar as brechas desse padrão de autorização, o que é fácil se você não seguir as recomendações básicas de segurança:

1. Sempre use o parâmetro `state` para evitar ataques do tipo CSRF (_Cross-Site Request Forgery_) nos quais o hacker tentaria se passar pelo servidor de autorização
2. Use um whitelist estrito de redirecionamento, nunca aceitando correspondências parciais
3. Utilize validação cruzada das credenciais, vinculando a mesma client id às requisições de concessão e de tokens
4. Garanta que as credenciais dos clients confidenciais jamais sejam distribuídas indevidamente 

Na verdade, a grande crítica dos especialistas em segurança cibernética ao OAuth é que não há vinculo nenhum entre os tokens de acesso e os usuários que os possuem, de modo que basta passá-los adiante para que funcionem, parte disso é resolvido com os JWT já que eles não são adulteráveis, mesmo assim, basta extraí-los e usar como `Bearer`.

O OAuth tem muitos casos de uso e resolve muito problemas no cenário enterprise, como a gestão de permissões cominadas gerais (Coarse grained) e específicas (Fine grained), desacopla as políticas de autorização da autenticação, é ótimo para ceder e revogar permissões, garante que apenas dispositivos gerenciados ou em conformidade possam acessar APIs específicas além de outras vantagens

Algo importante para se ter em mente é que o OAuth não é um protocolo de autenticação e não diz nada sobre o usuário, tratando apenas do uso e validação de tokens para acessar recursos e definitivamente não é feito para a autenticação, apesar de ter sido usado dessa forma como uma "gambiarra" por algum tempo, o processo era solicitar permissão para acessar a conta do Facebook, e usar o endpoint `/me` para pegar informações do perfil do usuário e identificá-lo, isso era chamado de pseudo autenticação.

Para evitar essa "gambiarra" foi criado, unindo conceitos do OAuth 2.0, Facebook Connect e SAML 2.0, o OpenID Connect (OIDC) com um novo `id_token` assinado para o `Client` e um endpoint `UserInfo` para solicitar os atributos do usuário, provendo uma série de scopes como `profile`, `email`, `address` e `phone`.

O grande trunfo desse modelo é ser completamente dinâmico, você insere o seu email e então o seu provedor OIDC pode ser dinamicamente descoberto, os metadados podem ser dinamicamente baixados e o `Client` pode saber dinamicamente quais os certificados serão utilizados e permitir BYOI (Bring Your Own Identity), um modelo de autenticação digital que permite aos usuários acessar novos serviços usando suas credenciais de provedores externos, como o Google.

A requisição inicial no OpenID é basicamente a mesma que no OAuth, exceto que inclui escopos padrão, por exemplo:

```HTTP
GET https://accounts.google.com/o/oauth2/auth?
scope=**openid email**&
redirect_uri=https://app.example.com/oauth2/callback&
response_type=code&
client_id=812741506391&
state=af0ifjsldkj
```

E obteria como resposta:

```HTTP
HTTP/1.1 302 Found<br>
Location: https://app.example.com/oauth2/callback?code=MsCeLvIaQm6bTrgtp7&state=af0ifjsldkj
```

No back channel uma requisição seria feita usando o código de concessão recebido:

```HTTP
POST /oauth2/v3/token HTTP/1.1
Host: www.googleapis.com
Content-Type: application/x-www-form-urlencoded

code=MsCeLvIaQm6bTrgtp7&client_id=812741506391&
  client_secret={client_secret}&
  redirect_uri=https://app.example.com/oauth2/callback&
  grant_type=authorization_code
```

E receberia como retorno:

```HTTP
{
  "access_token": "2YotnFZFEjr1zCsicMWpAA",
  "token_type": "Bearer",
  "expires_in": 3600,
  "refresh_token": "tGzv3JOkF0XG5Qx2TlKWIA",
  "id_token": "eyJhbGciOiJSUzI1NiIsImtpZCI6IjFlOWdkazcifQ..."
}
```

Com os tokens em mãos, o `Client` baixa dinamicamente as chaves de criptografia do servidor de autenticação num endpoint `JWKS` e valida a assinatura do JWT (`id_token`) e suas principais claims que já apresenta informações sobre o usuário no payload, caso sejam necessárias mais informações, o `Client` pode usar o `access_token` para acessar o endpoint `/userinfo` do provedor.

Um exemplo extremamente simples e fictício, tanto do `OAuth 2.0` como `OpenID Connect` foi implementado com `README.md` descritivo e comentários explicando algumas coisas no seguinte repositório do GitHub: https://github.com/yangclima/OAuth-Based-Auth 