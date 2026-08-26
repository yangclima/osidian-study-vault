
> https://www.jwt.io/introduction#what-is-json-web-token

JSON Web Token (JWT) é um padrão aberto de que define um compacto e auto contido método de trocar informações entre duas partes de forma segura usando um [[JSON API|Objeto JSON]], as informações trocadas podem ser verificadas através de assinaturas digitais , já que os JWT podem ser assinados seja com uma senha única (Algoritmo HMAC) ou um par de chaves pública e privada (Algoritmos RSA ou ECDSA).

Enquanto a assinatura digital garante a origem dos tokens e que os dados não foram alterados entre a origem e o final do caminho, a encriptação dos mesmos garante que ninguém que intercepte esses tokens será capaz de ler as informações neles condidas.

Esses tokens, são úteis principalmente em dois cenários:

1. O primeiro cenário da aplicação dos JWT é na autorização, uma vez que fazemos login numa aplicação, recebemos um JWT de identificação e o anexamos a cada requisição para nos identificar frente ao servidor.
2. O segundo cenário de aplicação é a troca de informações, já que a aplicação dos JWT garante a integridade dos dados (assegurando que não foram modificados) e a autenticidade da origem, embora os dados de um token puramente assinado continuem visíveis.

Na sua forma compacta, os JWT consistem em 3 partes separadas por `.`:

```
Header.Payload.Signature
```

Sendo elas:

 Como primeira parte do `Header`, o cabeçalho de um JWT consiste em duas partes, o tipo do token (Que obviamente é "JWT") e o algoritmo de assinatura usado 
 
```
{
  "alg": "HS256",
  "typ": "JWT"
}
```

Esse objeto então é codificado em `Base64Url` para formar a primeira parte do token. 

A segunda parte, o `payload`, é quem contém as claims, declarações sobre uma entidade, tipicamente, o usuário, e dados adicionais, podendo ser classificadas em 3 tipos:

1. Claims Registradas: Um conjunto de claims predefinidos que embora não sejam obrigatórios são recomendados, alguns deles são `iss` (issuer), `exp` (Tempo de expiração), `sub` (Subject), `aud` (Audience).
2. Claims Públicas: Claims voltadas para uso comunitário/padronizado e devem ser registradas ou usar URIs para evitar colisões.
3. Claims Privadas: O conjunto de claims criado para compartilhar informações entre as partes que concordaram em usá-los e não são nem claims públicas e nem claims registradas.

Assim como o `Header`, o `Payload` é codificado em `Base64Url`, formando a segunda parte do JSON Web Token.

A `signature`, por sua vez, é formada utilizando a versão codificada em `Base64Url` do `Header` e do `Payload` e codificando-os usando o algoritmo especificado no `header` com uma `Secret` desejada, por exemplo, se o algoritmo fosse `HMACSHA256` usaríamos o seguinte para criar a signature:

```
HMACSHA256(
Header + "." + Payload,
Secret)
```

Essa assinatura será então usada para verificar se as informações do token não foram alteradas na transmissão.

Agora que sabemos qual o formato geral do JWT, como ele é aplicado? No processo de autenticação, o fluxo clássico é o seguinte:  Ao fazer login com suas credenciais, um JWT é retornado, esse token então é adicionado aos headers de cada [[O que é HTTP|requisição]] sempre que você quer acessar um rota ou recurso protegido, seguindo o formato:

```
Authorization: Bearer <JWT>
```

Esse método funciona, em certos casos, como uma forma de autorização stateless, atendendo a um dos princípios das [[API Rest]]. A lógica das rotas protegidas checa pela existência de uma header de autorização com um JWT, caso ele exista, a validade do JWT é verificada e a requisição é aceita e processada, caso contrário, o usuário recebe um `401 Unauthorized`. 

Em alguns casos, os dados contidos no payload até evitam a necessidade de consultas ao banco de dados, porém, isso precisa ser usado com cuidado, primeiro, para não ficar um payload gigantesco, até por que alguns navegadores proíbem headers maiores que 8 kB e segundo, por que, uma vez gerado, o token será válido até expirar, se os dados mudam mais rápido que o tempo de expiração do token, isso será um problema.

![[ber_003.png]]

Seguindo o fluxo da imagem:

1. O Cliente faz uma requisição para o Servidor de autenticação, enviando suas credenciais através de algum dos fluxos de autenticação
2. O servidor verifica a validade das credenciais e caso elas sejam válidas ele retorna um token de autorização
3. A partir daí, o cliente passa a usar o token obtido para acessar os recursos protegidos


No que seria a etapa 4, o servidor que recebe uma requisição com um header contendo um JWT precisa realizar dois processos distintos: JWT Validation e JWT Verification. Na primeira, o objetivo é verificar se o JWT é de fato um token válido, bem formado, verificando aspectos como suas constituição de 3 partes, se ele tem um encoding em `Base64Url` válido e os claims esperados bem como se ele não está expirado, na segunda parte, a verificação, queremos saber se aquele token não foi adulterado e vem de uma fonte confiável, para isso, verificamos a assinatura e aspectos das claims, como se de fato o JWT vem de um issuer válido.

> https://curity.io/resources/learn/jwt-best-practices/

Os JWTs se tornaram tão difundidos que as vezes trabalhamos com eles com a falsa sensação de que eles são seguros simplesmente por que são JWTs, é importante ter em mente, no entanto, que a própria RFC que define o padrão de funcionamento desses tokens é simplesmente sobre como você pode estruturar uma mensagem e adicionar sobre ela camadas de segurança que protegerão a integridade ou mesmo o conteúdo dela, isto é, o que torna os JWTs seguros é a forma como você os usa.

É importante notar que a estrutura que citamos acima, com os JWTs formados por `Header`.`Payload`.`Signature` é a estrutura dos JWS (A versão Signed dos JWTs), mas existe também a versão encriptada, os JWE, formados por 5 partes: O `Header`, a `Encrypted Key`, o `Initialization Vector`, o `Ciphertext` (Payload) e a `Authentication Tag`.

Quanto aos casos de uso, existem dois principais aplicações para os JWTs, como Id Tokens, servindo para a identificação do usuário que o possui, voltado aos desenvolvedores dos clientes (O seu frontend é quem deve ler esse token) e como Access Token, servindo como um atestado de que ações você pode realizar e voltado aos desenvolvedores das APIs (O seu backend é quem deve ler esse token).

Levando em conta esses casos de uso, precisamos ter algumas coisas em mente:

1. Como os clientes podem começar a usar os dados desses JWTs em suas implementações, como extrair o nome do usuário e email para criar uma UI de profile, modificar a estrutura do payload pode quebrar essas implementações
2. Como normalmente aplicamos os JWS, qualquer um pode decodificar o payload e acessar as informações internas do token, por isso, precisamos evitar usar informações sensíveis nesses tokens por questões de privacidade do usuário
3. Além da privacidade do usuário, considere a privacidade da sua aplicação, evite disponibilizar qualquer informação sensível no payload do token, como chaves de API assim como informações sobre a implementação interna da aplicação, como as linguagens usadas e etc.
4. Como normalmente os JWTs são usados como bearer tokens a aplicação aceita qualquer requisição que contenha um token válido, independente de como quem está fazendo a requisição conseguiu esse token, se isso for um problema no seu use case existem padrões que podem ser usados para evitar isso, como implementações de PoP (Proof of Possession)
5. Enquanto os tokens de acesso podem ser substituídos facilmente por tokens opacos, os de identificação tem sempre de ser JWTs comuns, por isso é necessária atenção redobrada às informações que você disponibilizará no payload, nesse sentido, por mais que encriptar o token pareça uma solução, configurar isso e manter em funcionamento é muito mais complicado e requer muito mais trabalho que simplesmente forçar o seu usuário a buscar as informações do usuário num endpoint da API ao invés do payload do JWT
6. Quanto ao algoritmo usado para encriptar ou assinar seu token, a IANA mantém [uma lista com todos os algoritmos disponíveis para isso](https://www.iana.org/assignments/jose/jose.xhtml#web-signature-encryption-algorithms) contendo também recomendações que quais usar, em geral, são recomendados algoritmos com chaves assimétricas como `EdDSA` ou `ES256`, se for indispensável usar chaves simétricas, uma opção, apesar de menos segura é o `HS256`, se quiser uma padrão mais alto de segurança, vale a pena dar uma olhada nas recomendações do [Guia para Financial-Grade APIs](https://openid.net/specs/fapi-2_0-baseline.html#name-cryptography-and-secrets)
7. A regra de ouro é sempre validar o seu JWT, apesar da possibilidade de simplesmente consumir as informações decodificadas do payload, nesse sentido, mesmo que você use uma rede privada para que seu serviços se comuniquem, use verificação para os JWTs, é comum migrar serviços para uma rede aberta e o funcionamento inicial ser legado
8. Uma outra recomendação é fixar o algoritmo de encriptação para evitar ataques onde alguém tente passar como válido um token com um algoritmo `alg: none` ou com um protocolo mais fraco de encriptação.
9. Um dos principais ataques contra servidores que usam verificação de chaves assimétricas é o ataque de substituição de issuer, o hacker substitui o issuer do payload para um servidor próprio então o código de verificação acessa o próprio servidor do hacker para encontrar as chaves públicas de modo que obviamente o JWT malicioso passará na verificação, por isso é importante especificar o servidor usado para obtenção da chaves públicas no próprio código além de verificar o issuer com base numa allow-lista explícita.
10. É recomendado verificar também a audience para a qual o token foi destinado para evitar outros vetores de ataque, verificando com base numa allow-list a validade da `aud` do token
11. Uma outra recomendação é garantir que os tokens sejam usados para o propósito para o qual foram criados, isto é, garantir que um Id token sejam usado para identificação e somente para isso e que um access token seja usado para controle de acesso e somente para isso, isso pode ser implementado com lógicas de verificação das claims ou inserindo uma tag `type` ou similar no payload.
12. Por vezes, algumas claims do header do JWT podem conter informações sobre as chaves e criptografia da assinatura, como nas chaves `kid`, `jku` ou `x5c`, você não deve confiar cegamente nesses valores e deve implementar uma camada de checagem que garante a validade e origem desses valores
13. É recomendado usar o tempo de expiração do JWT o menor possível, no máximo minutos ou horas sempre que possível e lembrar que podemos basear a verificação do tempo de expiração do token em diversas claims, como `exp` (Expiration time), `nbf` (Not Before) ou `iat` (Issued At).
14. Ao assinar um JWT todas as informações do Payload e do header são consideradas e pertencem a assinatura, de modo que qualquer mudança resultará num erro de verificação, isso é inclusive utilizado, por meio de uma claim `jti` que funciona como um identificador único do token para que dois tokens nunca tenham a mesma assinatura, recomenda-se além disso, implementar o download dinâmico de chaves de criptografia públicas a partir de um endpoint de JSON Web Key Set do servidor de autorização para que o servidor consiga implementar rotação de chave sem quebrar a aplicação
15. Nunca use JWTs para sessões, essa é um péssima prática e reduz a segurança do seu servidor

Um exemplo extremamente simples e fictício foi implementado com `README.md` descritivo e comentários explicando algumas coisas no seguinte repositório do GitHub: https://github.com/yangclima/JWT-Based-Auth