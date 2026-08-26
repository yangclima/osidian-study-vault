O método de autenticação chamado de `Basic Authentication` é um método de autenticação simples e muito antigo, estabelecido na [RFC 7617](https://www.rfc-editor.org/rfc/rfc7617.html) e consiste numa autenticação orquestrada junto ao navegador do cliente e na passagem dos dados através de um header `Authorization`.

Ocorrendo nos seguintes passos:

1. Quando o browser tenta acessar o servidor, o servidor procura o header `Authorization` na requisição, não encontrando, emite um status code `401 Unauthorized` anexando também na requisição, um header `WWW-Authenticate` com um valor que inicia com `Basic`, simbolizando para o navegador que ele deve disparar o fluxo de autorização local de Basic authentication seguido de um valor `realm='<group_of_pages>` que ajuda a dar contexto ao usuário e serve para isolar diferentes grupos de páginas no navegador, ou seja, o servidor recusa a conexão e envia

```HTTP
HTTP 1.1 401 Unauthorized
WWW-Authenticate: Basic realm='<group_of_pages>'
```

2. Ao receber o `WWW-Authenticate` o navegador exibe um prompt para o usuário solicitando email e senha e quando o usuário preenche os campos, o navegador envia uma requisição contra o mesmo endpoint anexando o header `Authorization: Basic <base64_encoded_username>:<base64_encoded_password>` 
3. O server faz o parsing extraindo o header e verifica na base de dados se o conjunto de username e password estão registrados e, se estiverem, permite o acesso

Todo esse fluxo ocorre antes mesmo de entregar o frontend ou renderizar algo, sendo simples e gastando poucos recursos computacionais, 