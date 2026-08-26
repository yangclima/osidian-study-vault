Como o JS tem tipagem dinâmica e fraca ele não te impede de atribuir objetos ou primitivas de diferentes tipos a um mesma variável ao longo do fluxo do programa, o TS, por outro lado o faz e enquanto o valor de uma variável pode mudar, geralmente seu tipo não pode. Por exemplo:

```ts
let x = 12;

x = 'a';
// Erro: Type 'string' is not assignable to type 'number'.
```

Esse tipo de erro pode ser resolvido trocando o tipo inferido, que é igual ao tipo do valor inicialmente atribuído, por um union type (No exemplo, teríamos `let x: number | string = 12`), entretanto, em geral, fazer isso trás diversos efeitos negativos para o seu código.
Primeiro que, em geral, union types são mais difíceis de lidar que tipos primitivos, segundo que geralmente quando fazemos isso estamos associando valores com diferentes significados à mesma variável o que dificulta a ação do type checker e também dos leitores.

Nesse sentido, fica a regra: Para evitar problemas com o Type Checker e com os leitores humanos, evite reusar uma mesma variável para valores de diferentes tipos.