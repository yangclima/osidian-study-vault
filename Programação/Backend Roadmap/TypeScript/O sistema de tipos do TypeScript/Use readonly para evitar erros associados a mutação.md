Um dos bugs mais comuns, clássicos e difíceis de identificar são aqueles associados a [[Mutabilidade e Imutabilidade]] dos objetos, sobretudo em linguagens como JS e Python. Um exemplo é quando passamos um array para uma função, não estamos passando um objeto propriamente dito, mas um endereço de memória, de modo que o que for feito dentro da função pode alterar o objeto passado e gerar problemas e inconsistências.

Um modo de evitar esse tipo de problema no TS é usando o modificador `readonly`, aplicado para declarar que uma determinada propriedade ou variável é somente para a leitura.

```ts
interface PartlyMutableName {
 readonly first: string;
 last: string;
}

const jackie: PartlyMutableName = { first: 'Jacqueline', last: 'Kennedy' };
jackie.last = 'Onassis'; // OK
jackie.first = 'Jacky';
// Erro: Cannot assign to 'first' because it is a read-only property.
```

Além disso, como é comm precisar evitar atribuições para todas as propriedades o TS fornece um tipo genérico utilitário `Readonly<T>` que basicamente define como read-only todas as propriedades de um objeto, esse tipo no entanto é raso e não marca como read-only as propriedades das propriedades, o que pode ser feito com o tipo `DeepReadonly` da library `ts-essentials`.

É importante ter em mente que apesar de `readonly` impedir de reatribuir um valor, ele não impede que o valor seja mutado, não impede que você use os métodos internos se uma string, por exemplo, para modificá-la.

Por esse motivo, em geral, para termos uma versão mutável e uma imutável de uma classe precisamos de classes separadas, justamente por isso existem por padrão as interfaces `Array<T>` e `ReadonlyArray<T>` o primeiro sem os métodos de mutação e o segundo com que podem ser declarados como `T[]` e `readonly T[]` respectivamente, sob o ponto de vista dos [[Pense nos tipos como conjuntos de valores|tipos como conjuntos]], o array normal é um subconjunto de array read-only e portanto pode ser atribuído a uma variável cujo tipo é um array desse tipo, enquanto o contrário não é verade.

Nesse contexto e dadas as ferramentas existentes, se uma função toma um argumento e não o modifica, é uma boa prática marcá-lo como `readonly` para deixar claro para os usuários da função que o argumento não é modificado.

