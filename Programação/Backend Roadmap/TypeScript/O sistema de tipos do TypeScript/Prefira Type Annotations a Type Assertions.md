No TS temos duas formas de atribuir um tipo a uma variável, as *Type Annotations* as `Type Assertions`:

```ts
interface Person {
  name: string
}

// Type Annotation
const yan: Person = {name: "Yan"};

// Type Assertion
const lima = {name: "Lima"} as Person;
```

O resultado final é o mesmo, atribuímos o tipo `Person` a ambas as variáveis do exemplo, porém, de formas muito diferentes, a primeira opção atribui o tipo e garante que o valor atribuído esteja em conformidade com ele, enquanto o segundo que diz ao TS que, independente do tipo inferido, você sabe mais e quer que o valor seja considerado do tipo especificado, isto é, não checa se o valor atribuído está em conformidade com o tipo. 

Desse modo, ao tentar atribuir um tipo que não está em conformidade com `Person`, digamos, um objeto vazio, teríamos:

```ts
const yan: Person = {};
// Erro: Property 'name' is missing in type '{}' but required in type 'Person'

const lima = {name: "Lima"} as Person; 
// Sem Erro
```

Daí já fica óbvio que devemos usar sempre as Type Annotations, afinal, usando as type assertions estamos cegando o TS aos nossos erros.

Além dos erros de inconformidade do tipo mais óbvios, o TS também apontará um erro se tentarmos atribuir a uma variável um objeto que contém propriedades não listadas no tipo, isso ocorre mesmo contradizendo a [[Familiarize-se com a tipagem estrutural|tipagem estrutural]] por que isso geralmente é um erro, há entretanto formas de contornar isso usando type annotations mas não usando type assertions.

Ademais, as asserções só funcionam quando o valor que sofre a asserção for um [[Pense nos tipos como conjuntos de valores|subconjunto]] do tipo da asserção, caso contrário o TS entenderá a asserção como erro e te obrigará a usar uma asserção dupla,  primeiro para `unknown` e só depois para o tipo, isto é, `1 as Person` mostrará o erro `Conversion of type 'number' to type 'Person' may be a mistake because neither type sufficiently overlaps with the other.` então precisaremos usar `1 as Unknown as Person` o que ajuda a garantir que a asserção não é um erro.

Dado os fatos acima descritos, fica a regra de que devemos utilizar sempre as anotações de tipo ao invés das asserções a menos que tenhamos uma razão específica para fazer o contrário.

Um ponto importante sobre essas asserções é saber utilizar esse recurso para as arrow functions, seguido o seguinte:

```ts
const people = ['alice', 'bob', 'jan'].map(name => ({name}));
// Tipo inferido é `{name: string;}[]` mas deveria ser `Person[]`

// A forma errada - Não use Type Assertions
const people = ['alice', 'bob', 'jan'].map(
 name => ({name} as Person)
);

// Uma forma correta
const people = ['alice', 'bob', 'jan'].map(
  name => {
    const person: Person = {name};
    return person;
  }
);

// Uma forma correta mais simples seria:
const people = ['alice', 'bob', 'jan'].map((name): Person => ({name}));
// Perceba que os parênteses de (name) são importantes para distinguir de uma tipagem para o próprio name e não para o retorno da função
```

Um caso de uso que pode justificar a aplicação de uma asserção é o caso em que temos um determinado valor que temos certeza que é não nulo, então, podemos usar uma asserção, por exemplo:

```ts
const elNull = document.getElementById('bar');
// Tipo Inferido: HTMLElement | Null

const el = document.getElementById('bar') as HTMLElement;
// Tipo Inferido: HTMLElement 
```

Uma alternativa a isso é usar a asserção e tipo não nulo `!`, interpretado como tal quando usado como sufixo (Quando usado como prefixo ele é [[Saiba identificar se um símbolo pertence ao espaço de valores ou de tipo|interpretado]] como o operador lógico de negação do JS), assim, usamos:

```ts
const el = document.getElementById('bar')!;
// Tipo Inferido: HTMLElement 
```

Essa notação deve ser preferida à asserção com ``as Type``, já que ainda valida a parte não nula do tipo, porém, ainda assim, só deve ser usada se tivermos certeza que no caso de uso o valor atribuído à variável é não nulo.

Uma outra prática comum é utilizar o optional chaining operator do JS `?` para acessar propriedades de objetos possivelmente nulos, diferente de `!` esse operador é do espaço de valores e não se trata de uma asserção de tipo, em geral, sua utilização é mais segura que a do operador `!`, mesmo assim, pondere sobre sua utilização, já que ele evita erros de acesso de propriedades que em alguns casos deveriam ser rastreados.

Como regra geral, as asserções só devem ser usadas quando tivermos certeza que sabemos de algo que foge do contexto de nosso código disponível ao TS, isto é, sabemos algo que o TS não sabe, como um valor que com certeza pertence a um tipo dado que o contexto externo que só nós temos acesso diz isso, além disso, recomenda-se utilizar nesses caso um comentário descritivo explicando o motivo da utilização da asserção.