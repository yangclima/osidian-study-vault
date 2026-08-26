Todos sabemos que o [[JavaScript]] está cheio de peculiaridades no que tange, sobretudo, a coerção automática  de tipos que gera coisas como `"0" == 0` sendo avaliado como True, sabemos inclusive que o [[Entenda a relação entre TypeScript e JavaScript|TS surgiu justamente para evitar problemas com esse tipo de coisas no JS]] ao criar tipos e [[Prefira alternativas mais precisas às Index Signatures|index signatures]], em especial, tem um problema relacionado que devemos evitar.

Basicamente, como já sabemos, as chaves dos objetos JS permitem os tipos `string`, `number` e `symbol`, porém, na realidade o tipo `number` é como uma concessão para permitir a existência dos arrays como objetos JS, isso é dito pois, na realidade, os `number` atribuídos como chaves de um objeto são convertidos automaticamente para ``string``, tanto que:

```js
console.log({1: 'a', 2: 'b', 3: 'c'})

// Saída: { '1': 'a', '2': 'b', '3': 'c' }
```

Esse comportamento e a relação entre Array e Objeto é modelado no TS em `lib.es5.d.ts` como:

```ts
interface Array<T> {
  // Declaração dos métodos internos do Array
  
  [n: number]: T;
}
```

Esse é mais um ponto da declaração  "[[Saiba identificar se um símbolo pertence ao espaço de valores ou de tipo]]", em runtime as chaves dos objetos, como manda a especificação ECMAScript são convertidas como ``string``, porém tipar essas chaves como `number` ajuda a evitar erros e declarações feitas sem intenção.

Perceba então que usar números como chaves de um objeto ou como tipo de uma index signature trás a falsa sensação e erro conceitual de que de fato eles serão tratados como números pelo JS e nesse sentido fica a regra geral de não utilizar, afinal, se você pensa em usar números como chave, provavelmente seu código fará mais sentido com um tuple ou com Array.

Se você realmente deseja aceitar tuplas de qualquer tamanho ou qualquer estrutura semelhante a um array, o TypeScript possui um tipo `ArrayLike` que você pode utilizar e que tem como exigências apenas uma propriedade `length` e chaves numéricas.