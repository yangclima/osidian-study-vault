O TypeScript adiciona um novo espaço, o espaço de tipos, enquanto o JS possui naturalmente o espaço de valores, esse espaço só existe em tempo de compilação e para de existir no código JS transpilado.

É essencial ter isso em mente por que existem inúmeros símbolos, isto é, palavras reservadas e notações que existem em ambos os espaços e tem diferentes significados em cada um desses espaços. 

Um erro comum ocorre quando tentamos, por exemplo, em runtime, nos referir a objetos que existem apenas no espaço de tipos, por exemplo, dado que existe um tipo `Square` tentar checar uma variável `shape instaceof Square`, o que não faz sentido já que o operador `instanceof` só é capaz de operar sobre valores.

Como exemplo, sabemos que `type MinAvailability = 4` é uma declaração no espaço de tipos, enquanto `const MinAvailability = 4` é uma declaração do espaço de valores, de modo similar, uma única declaração pode ter partes no espaço de valores e partes no espaço de tipos, por exemplo:

```ts
function calculateVolume(shape: Shape): number {
//       --------------- -----                    -> Espaço de Valores
//                            -------   -------   -> Espaço de tipos
}
```

Outro exemplo importante é o operador `typeof` que existe em ambos os espaços mas que no espaço de de tipos se referente ao tipo TS declarado de um valor e no espaço de valores se refere ao tipo primitivo ao qual pertence o valor em runtime.]

Outros operadores ambíguos nesse sentido são:

1. O `[ ]`, usado para acessar uma propriedade de um objeto é usando no espaço de tipos para acessar o tipo de uma propriedade de um outro tipo e em runtime para acessar valores de objetos iteráveis
2. O `this` em runtime é usado para se referir ao objeto que está executando no momento enquanto no TS ele é usado para criar uma tipagem polimórfica 
3.  No espaço de valores `|` e `&` são respectivamente os operadores bitwise AND e OR
4. No espaço de valores o `const` cria uma nova variável enquanto no espaço de tipos `as const` muda o tipo inferido
5. No espaço de tipos `extends` define uma subclasse enquanto no espaço de tipos ele define um subtipo ou define uma constraint sobre generic types.
6. No espaço de tipos `in` é usado em for loops e no espaço de tipos ele é usado nos chamados tipos mapeados
7. No espaço de valores `!` é o operador lógico de negação enquanto no espaço de tipos ele é uma asserção de tipo não nulo.

Problemas podem surgir também com relação a desestruturação e a definição de tipos, isto é, não é possível tipar, o seguinte código, por exemplo, retornará erro por que `string` está sendo interpretado como uma variável

```ts
const {username: string, age: number, email: string} = {
  username: "John Doe",
  age: 30,
  email: "John.Doe@example.com"
}
```

O correto seria:

```ts
const {
  username,
  age,
  email,
}: { username: string; age: number; email: string } = {
  username: "John Doe",
  age: 30,
  email: "John.Doe@example.com",
};
```


