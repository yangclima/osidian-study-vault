O TypeScript é uma linguagem extremamente opinativa e permite que muito da forma como atua e processa o código seja especificado pelo usuário, seja através de flags no comando que chama o compilador (`tsc`) ou através do arquivo de configuração (`tsconfig.json`), por isso, a resposta para a pergunta "esse código irá gerar um erro no TypeScript?" é quase sempre um "depende".

Uma dica é optar sempre pela utilização do arquivo de configuração e manter o arquivo `tsconfig.json` na raiz do seu repositório e inclusive enviá-lo para o seu repositório remoto, isso permitirá que as configurações do TS sejam compartilhadas e uniformes entre todos os colaboradores e ferramentas utilizadas, esse arquivo pode ser gerado automaticamente usando o comando `tsc --init`.

Atualmente são mais de 100 opções disponíveis para configurar o seu compilador TS, apesar disso, se destacam duas: `noImplicitAny` e `strictNullChecks`.

A opção `noImplicitAny` especifica o que o TypeScript deve fazer quando não for capaz de determinar o tipo de uma variável, caso a opção esteja desativada a variável simplesmente será inferida como `any`, o que pode, potencialmente, gerar problemas catastróficos no seu programa já que ter uma variável marcada como ``any`` basicamente desativa o type checker para o código que envolve essa variável. Esses `any` são ditos **implícitos** por que você não especificou de forma explícita que uma variável tem o tipo `any`. 

```ts
// Com noImplicitAny 
function add(a, b) {
  // Erro: Parameter 'a' implicitly has an 'any' type
  // Erro: Parameter 'b' implicitly has an 'any' type 
  return a + b
}

// Sem noImplicitAny
function add(a, b) {
  return a + b // OK
}
```

Basicamente é fundamental ter sempre essa opção ativa já que a grande ajuda que o TypeScript provê decorre justamente da checagem de tipos e a linguagem se torna extremamente permissiva sem ela, deixando de resolver justamente o problema para o qual ela foi idealizada, só é tolerável ter essa opção desativada em repositórios que estão sendo transicionados do  JS para o TS e só durante a transição.

A segunda opção a `strictNullChecks` controla se os valores `null` e `undefined` são permitidos em todos os tipos, sem ela, o valor `null` é, por exemplo, permitido para uma variável mesmo que ela seja explicitamente tipada como, digamos, `number`, entretanto, essa regra é o pesadelo dos novos usuários, já que para garantir evitar erros do TS com relação a essa regra e evitar que o valor null seja atribuído indevidamente você precisará utilizar verificações e asserções e de fato garantir que em nenhum dos casos e caminhos de execução do seu código esses tipos possam ser atribuídos as variáveis.

```ts
// Com strictNullChecks 
const x: number = null;
// Erro: Type 'null' is not assignable to type 'number'

// Sem strictNullChecks
const x: number = null; // OK
```

Apesar de aumentar a dificuldade da linguagem usar essa opção facilita muito o rastreamento de erros que envolvem os valores do tipo `null` e `undefined`, essa regra é menos essencial que a primeira mas deve de preferência ser sempre utilizada, é importante então utilizá-la desde o início já que quanto mais extenso for sua codebase mais difícil será depois para começar a usar essa regra.

Existem ainda outras opções interessantes como `noImplicitThis` ou `strictFunctionTypes`, todas menos essenciais que as duas primeiras e uma boa parte delas são automaticamente ativadas quando usamos a opção `strict` que vem por padrão ao executar `tsc --init`, usando essa opção o TS será capaz de detectar a maior parte dos erros mais comuns e é extremamente recomendado que você a use.

Existem ainda opções que deixam a checagem do TS ainda mais agressiva como a opção `noUncheckedIndexedAccess` que evita erros no acesso de índices de arrays e objetos, além de muitas outras opções.

A dica que fica então é: Saiba as configurações que você está usando e esteja atento a elas e as suas implicações, use sempre `noImplicitAny` e `strictNullChecks` além de, sempre que possível, usar `scrit`.

