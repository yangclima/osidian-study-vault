Em geral, um valor no JS é considerado ou um objeto ou um dos 7 tipos de valores primitivos da linguagem: `number`, `string`, `boolean`, `bigint`, `symbol`, `null` e `undefined`, caracterizados pela ausência de métodos. 

Ok, mas se eles não tem métodos internos por que eu posso usar `"Yan Lima".split(" ")` ou então `"Yan".charAt(0)`? Esse é um comportamento interessante do JS, chamado de Autoboxing. Basicamente o JS usa Object Wrappers, ou empacotadores, um objeto temporário.

Basicamente quando você tenta acessar um método de um valor primitivo o JS automaticamente encapsula aquele primitivo num Object Wrapper correspondente ao tipo de valor primitivo (`String` para `string`, `Number` para `number` e por aí vai), esses objetos tem os métodos internos do tipo então você os acessa e em seguida o objeto é jogado fora.

Vale ressaltar que os primitivos `null` e `undefined` não tem wrappers.

O TypeScript modela esse comportamento disponibilizando os tipos primitivos e também os tipos dos Object Wrappers com a diferença única que os primitivos começam sempre com uma letra minúscula (`number`, `string`, `boolean`, `bigint`, `symbol`, `null` e `undefined`) e os wrappers começam com letra maiúscula (`Number`, `String`, `Boolean`, `BigInt` e `Symbol`).

É fácil confundir, mas devemos sempre usar os tipos primitivos a menos que tenhamos um ótimo motivo para fazer diferente,  a questão é que apesar de um valor primitivo ser atribuível a seu respectivo tipo wrapper o contrário não é verdade, além disso, a maioria dos módulos e bibliotecas externas usam os tipos primitivos.

Usando `typescript-eslint` com as regras recomendadas esses erros são evitados nas regras de ban.