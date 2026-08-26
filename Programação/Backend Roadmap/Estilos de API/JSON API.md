> https://jsonapi.org/

O padrão JSON:API é um padrão criado para estabelecer diretrizes de formatação e construção de payloads JSON para APIs que se comunicam usando esse padrão, criado de forma a estabelecer um padrão de objetos representacionais trocados entre cliente e servidor, de forma que, uma [[API Rest]] pode ser também uma JSON API.

Hoje em dia, esse padrão é pouco utilizado como um todo, por ser verboso e deixar os payloads muito pesados e difíceis de ler, porém, traz uma série de recomendações que se extraídas e processadas podem ter um grande impacto na forma como você escreve e entende os payloads da sua API.

São as recomendações do padrão JSON API:

1. Os nomes dos atributos dos objetos JSON devem ser nomeados usando apenas caracteres ASCII, começar e terminar com um caractere "`a-z`" e seguir uma estrutura camel case.
2. Ao definir a estrutura dos URIs dos recursos da sua API é útil considerar que todos os recursos residem num mesmo documento agrupados por tipo (Coleções) no nível superior desse documento, então, cada objeto individual que pertence a essas coleções tem um id único dentro dela que permite que ele seja univocamente identificado, então, se existe um tipo `foto` acessamos a coleção de todas as fotos usando `/fotos` e uma foto em específica usando `/fotos/{fotoId}`
3. Quanto ao formato das URIs para exibir os relacionamentos entre as entidades do sistema, o padrão diferencia requisições que tem como target um objeto relacionado a outro e as que tem como target as relações entre os objetos propriamente, por exemplo, se quisermos criar uma entidade ``foto`` associada a uma entidade ``autor`` usamos `POST /autores/{autorId}/fotos` mas se quisermos criar uma relação entre um autor que já existe e uma foto que já existe, usamos uma requisição contra `POST /autor/relationship/fotos`, esse `/relationship/` é o padrão definido pelo JSON:API
4. Nesse padrão, a filtragem de recursos é implementada usando o query parameter `filter`, numa sintaxe que segue `{url}?filter[{filter_param}]={value}`, por exemplo, podemos usar `GET /comentarios?filter[autor]={autorId}`, é permitido também uma uma lista separada por vírgulas para usar um filtro de múltiplos valores ou ainda múltiplos filtros como `GET /comentarios?filter[autor]=1,2&filter[post]=1` 
5. Embora não exista um padrão oficial, é recomendado seguir o formato `ISO 8601` para passar objetos de date/time via JSON.

Mas afinal, o que é, tecnicamente JSON? JSON (Java Script Object Notation) é um formato leve de intercâmbio de dados, construído totalmente agnóstico a linguagens mas usando uma sintaxe familiar as linguagens da família C, ele é feito para ser fácil para máquinas processarem e gerarem bem como para ser legível de forma fácil por humanos.

Um objeto JSON é construído em duas estruturas:

1. Um conjunto de pares `nome/valor` 
2. Uma lista ordenada de valores

No primeiro caso, usamos uma estrutura onde o objeto começa e termina com chaves (`{` e `}`), e cada par de ``nome``/``valor`` é composto por um ``nome`` separado por `:` do seu respectivo valor e então separado por `,` do próximo valor, sendo o ``nome`` uma string, e o ``valor``, uma string, um número, um array ou um objeto.

No segundo caso, usa-se uma estrutura onde a lista começa e termina com colchetes (`[`,`]`) e cada valor da lista é um número, string, objeto ou array, cada valor sendo separado por `,`.

