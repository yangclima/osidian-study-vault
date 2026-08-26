Enquanto a maioria dos tipos só se tornam cada vez mais restritos ao longo do code flow devido ao [[Entenda o type Narrowing|type narrowing]] existe um caso onde a inferência de tipos ocorre de modo que os tipos se tornam mais abrangentes sendo então chamados de evolving types.

Por exemplo:

```ts
const test = [];
// Tipo inferido

test.push(1);
// Tipo inferido: const test: any[]

test.push("1");
// Tipo inferido: const test: number[]

test.push([1]);
// Tipo inferido: const test: (number | string)[]

test;
// Tipo inferido: const test: (string | number | number[])[]
```

Note que, de fato, o tipo está evoluindo ao longo do fluxo de código, tornando-se cada vez mais abrangente. 

O primeiro ponto importante a se ter em mente sobre esse processo é que os tipos só evoluem através de escrita aplicada a eles e se você tentar lê-los antes que eles evoluam a partir de um `any` type isso irá gerar erros, por exemplo:

```ts
function range(start: number, limit: number) {
  const nums = [];
  // Erro: Variable 'nums' implicitly has type 'any[]' in some locations where its type cannot be determined
  
  if (start === limit) {
    return nums;
    // Erro: Variable 'nums' implicitly has an 'any[]' type
  }
  
  for (let i = start; i < limit; i++) {
    nums.push(i);
  }
  
  return nums;
}

```

Um outro fato importante é que os tipos não evoluem através de chamadas de função, por exemplo, um `forEach` executando o push sobre a lista, um ótimo motivo para preferir loops for-of no TS em detrimento de loops ``foreach``.

Os tipos capazes de evoluir são somente `null`, `undefined` e `[]`.

Por fim, é importante ter em mente as clássicas desvantagens de tipos inferidos, às vezes os tipo que o TS inferiu não bate realmente com o objetivo que você traçou para ele.

