O processo de [[Entenda como o tipo de uma variável é inferido|widening]] faz com que construir um objeto em pequenos passos gere alguns problemas isso por que os TS infere o tipo de uma variável com base no valor especificado na sua atribuição, nesse sentido, a dica é criar o objeto todo de uma vez.

Caso não seja possível criar o objeto todo de uma vez só, uma alternativa disponível é utilizar o spread operator, uma forma inclusive segura de fazer isso e com a qual o TS lida e infere os tipos bem, por exemplo:

```ts
const point = {x: 3, y: 3};
const id = {name: "Point"};

const namedPoint = {...point, ...id};
// Tipo inferido: { name: string; x: number; y: number;}
```

Por mais que isso seja trabalhoso demais para objetos simples, é uma técnica extremamente poderosa para trabalhar e mesclar tipos complexos permitindo que automaticamente o TS infira seu tipo.

Nesse mesmo sentido, surge nesse contexto a possibilidade de criar tipos com propriedades condicionais de modo que função em runtime e para a qual o TS é capaz de inferir bem os tipos, por exemplo:

```ts
let hasMiddleName: boolean = true;
const firstLastName = { firstName: "John", lastName: "Doe" };

  

const fullName = {
  ...firstLastName,
  ...(hasMiddleName ? { middle: "William" } : {}),
};
// Tipo inferido:  { middle?: string; first: string; last: string;}
```

Ou de forma mais concisa (Com o mesmo tipo inferido):

```ts
const fullName = {
  ...firstLastName,
  ...(hasMiddleName && { middle: "William" }),
};
```