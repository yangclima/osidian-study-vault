Basicamente, o TypeScript oferece todas as features do JavaScript, com um adicional: um sistema de tipos, o ponto é que, apesar de ter alguns tipos primitivos, o JavaScript não checa consistentemente a forma como você atribui esses tipos, e o TS resolve exatamente esse problema, ele verifica a atribuição de valores e garante que o código como um todo seja consistente com sua tipagem, diminuindo a chance de bugs e outros comportamentos inesperados.

# Tipos por inferência
Em muitos casos, você não precisa sequer declarar os tipos para uma variável, o TS conhece o JavaScript e tem plena capacidade de gerar alguns tipos simples por você, por exemplo:

```js
let helloWorld = "Hello World!";
```

Esse entendimento do JS é que permite que o TS consiga **inferir** que a variável `helloWorld` é do tipo `string` no código acima, além disso, quando usamos o VS Code, por exemplo, e temos várias opções de autocomplete compatíveis com o tipo das nossas variáveis devemos isso ao TypeScript, que é executado pelo VS Code por baixo dos panos e permite inferir o tipo a qual cada variável pertence.

# Definindo Tipos
Em alguns casos de uso é difícil inferir automaticamente os tipos, para resolver isso, podemos nós mesmos declará-los utilizando uma sintaxe especial que o TypeScript adiciona, por exemplo, podemos descrever a forma de um objeto `User` como um objeto que possui os atributos `username` (`string`) e `id` (`number`), usando a sintaxe:

```ts
interface User {
  id: number;
  username: string;
}
```

E então usar esse tipo para declarar que um determinado objeto deve seguir o formato estabelecido usando a sintaxe:

```ts
const user: User = {
  id: 135,
  username: 'Yan Lima'
};
```

E isso permitirá que o TS te avise e retorne erro caso você acabe tentando atribuir a essa variável um objeto que não corresponde ao tipo que você declarou, por exemplo, o código:

```ts
const user: User = {
  id: '135',
  username: 'Yan Lima'
};
```

Te mostrará como erro, o seguinte:

```
Type 'string' is not assignable to type 'number'.
```

E ainda te avisará:

```
The expected type comes from property 'id' which is declared here on type 'User'
```

Como o JS suporta programação orientada a objetos e o TS suporta o JavaScript inteiramente, podemos também usar as interfaces nas declarações de classe:

```ts
class UserAccount {
  id: number;
  username: string;
  
  constructor(id: number, username: string) {
    this.id = id;
    this.username = username;
  }
}

const user: User = new UserAccount(135, 'Yan Lima');
```

Além disso, podemos ainda usar essas interfaces para tipar retornos e parâmetros de funções, por exemplo:

```ts
function findUserById(id: number): User {
  // ...
}

function putUser(newUser: User): User {
  // ...
}
```

Além dos types primitivos padrão do JS (`number`, `bigint`, `undefined`, `boolean`, `null` e `symbol`) que você pode usar ao criar uma interface, o TS adiciona alguns tipos:

1. `any`: Permitir qualquer coisa
2. `unknow`: Garanta que alguém usando esse tipo declare qual tipo é
3. `never`: Não é possível que esse tipo aconteça
4. `void`: Uma função que retorna `undefined` ou que não tem valor de retorno

Para construir tipos, existem duas sintaxes `interface` e `type`, mas, em geral, você deve preferir o uso de `interface`, usando o `type` somente quando precisar de suas funcionalidades específicas.

# Compondo Tipos
Uma outra possibilidade no TypeScript é compor, construir tipos mais complexos a partir de tipos mais simples, podemos fazer isso usando `Unions` ou `Generics`.

## Unions
Com uma união você pode declarar que um determinado tipo pode ser um de vários outros, por exemplo:

```ts
type Numeric = bigint | number;
```

Nesse exemplo, criamos o type `Numeric` que pode ser um valor do tipo `bigint` ou um valor do tipo `Number`. Unions são muito usados para criar enums, por exemplo:

```ts
type Role = "consultor" | "gerente" | "diretor" | "assessor" | "presidente";
```

Além disso, podemos usá-los para permitir gerenciar tipos diferentes, por exemplo:

```ts
function length(obj: string | string[]){
  return obj.length;
}
```

Nesse exemplo, `obj` pode ser ou uma `string` ou uma lista de `string`, isso pode ser usado para gerenciar a lógica dentro de uma função ou classe usando `typeof`.

## Generics
Os `Generics` fornecem uma espécie de variável de tipos, um exemplo comum é o generic usado ao declarar um ``Array``. Enquanto um `Array` sem generic pode conter itens de qualquer tipo, se declaramos um array com generic conseguimos especificar o tipo de dado que pode ser armazenado ali.

```ts
type AnythingArray = Array<any>; // Pode conter qualquer coisa
type NumberArray = Array<number>; // Só pode conter Números
```

Outro caso de aplicação é para a criação de tipos genéricos baseados na manipulação de outros tipos, por exemplo:

```ts
interface Repository<ObjType> {
  create: (obj: ObjType) => ObjType;
  update: (obj: ObjType) => ObjType;
  delete: (obj: ObjType) => void;
  find: () => ObjType | ObjType[];
}
```

# Duck Typing 
Um fato importantíssimo sobre o TS é que ele usa o chamado Duck Typing, você não precisa declarar que um variável é de um dado tipo para que o TS o reconheça como tal, "Se nada, voa, anda e faz *Qua* é um pato", isto é, se um objeto, tipo ou estrutura possui tudo que um determinado tipo tem, ele é considerado como pertencendo àquele tipo, mesmo que não seja perfeitamente.