Basicamente o compilador TypeScript (`tsc`) realiza duas funções:

1. Transpila o código TS/JS moderno para uma versão antiga do JavaScript, compatível com navegadores e outros ambientes de execução
2. Verifica o código em busca de type errors

O mais importante sobre isso é que essas duas funções são completamente independentes, uma não afeta a outra e, portanto, os tipos no seu código não afetam a forma como seu código é executado. Essa propriedade tem diversas interessantes e surpreendentes implicações.

# Você não pode checar os tipos TS em runtime
Por mais que seja tentador, você não consegue utilizar os types declarados em TypeScript para verificar em tempo de execução o tipo ou instância das suas variáveis, por exemplo, veja o seguinte código:

```ts
interface Square { width: number };
interface Rectangle { width: number, height: number };

function calculateArea(shape: Square | Rectangle) {
  if (shape instanceof square) {
    // Erro: 'Square' only refers to a type, 
    //       but is being used as a value here.
    return shape.width * shape.width;
  } else {
    return shape.width * shape.height;
    // Erro: property 'height' does not exist on type 'Square | Rectangle'.
  }
}
```

Apesar de parecer legítimo, veja os erros indicados, isso é uma consequência direta da independência da checagem e do transpiling, o código que executa de verdade é a versão transpilada desse código, sem types, sem type annotations, sem interfaces e por isso não faz sentido tentar executar essas verificações usando `instanceof` ou `typeof`.

Uma solução para isso é usar a presença de uma propriedade capaz de distinguir os tipos, no exemplo acima, `height`, a função então ficaria:

```ts
function calculateArea(shape: Square | Rectangle) {
  if ('height' in shape) {
    return shape.width * shape.height;
  } else {
    return shape.width * shape.width;
  }
}
```

Mas e se não houver uma propriedade assim, que permita fazer essa distinção? Então podemos introduzir uma propriedade disponível em runtime capaz de fazer, no nosso exemplo, teríamos:

```ts
interface Square { width: number, kind: 'square' };
interface Rectangle { width: number, height: number, kind: 'rectangle' };

function calculateArea(shape: Square | Rectangle) {
  if (shape.kind === 'square') {
    return shape.width * shape.width;
  } else {
    return shape.width * shape.height;
  }
}
```

Nesse caso, o propriedade `kind` atua como uma tag e dizemos que o tipo `Square | Rectangle` é uma "tagged union" ou "discriminated union" que tem `kind` como discriminante, esse padrão é extremamente comum no TS.

Uma outra possibilidade é utilizar uma classe ao invés de um type ou interface, classes no TS geram tanto um valor que é disponível em runtime quanto um type que não é.


```ts
class Square {
  width: number;
  constructor(width: number) {
    this.width = width;
  }
}

class Rectangle {
  width: number;
  height: number;
  
  constructor(width: number, height: number) {
    this.width = width;
    this.height = height;
  }
}

function calculateArea(shape: Square | Rectangle) {
  if (shape instanceof Square) {
    return shape.width * shape.width;
  } else {
    return shape.width * shape.height;
  }
}
```

Nesse exemplo, ao usar `: Square | Rectangle` nos referimos aos tipos `Square` e `Rectangle`, por outro lado, ao usar `instanceof` nos referimos ao valor definido pelo construtor das classes.

# Códigos com erros de tipo podem produzir saídas
Devido a independência entre processos citada nesse texto, os erros no TS acabam sendo similares aos warnings em linguagens como o Java ou C, eles não impedem que o código sejam transpilado nem mesmo indicam com certeza que haverão exceções em runtime, isso não quer dizer, entretanto, que você deve ignorá-los, na verdade, quase sempre eles indicam algo que será potencialmente um problema e vale sempre a pena investigá-los, não caia na armadilha de commitar um código com erros de tipo, se esses erros existem você cometeu alguma confusão ao declarar os tipos no seu código.

Um erro comum nesse contexto é dizer, erroneamente, que seu código TS "Não compila", se referindo-se ao fato dele apresentar erros, já vimos entretanto que essa terminologia é incorreta, por isso, prefira dizer que ele tem erros ou simplesmente que ele não está passando no type checking.
# Operações de Tipo não afetam valores em runtime
Algumas vezes é possível ver type assertions sendo usadas de forma errada como casting, por exemplo:

```ts
function asNumber(val: number | string): number {
 return val as number;
}
```

Nesse caso `as number` (O type assertion) não faz nada além de dizer "assuma que `val` é do tipo `number`" para o compilador, trata-se de uma operação de tipo e portanto não afeta de forma alguma o valor de `val` em runtime, a forma correta de escrever seria então:

```ts
function asNumber(val: number | string): number {
 return Number(val);
}
```
# Os tipos em runtime podem não ser iguais aos tipos declarados
Veja a função:

```ts
function setLightSwitch(value: boolean) {
 switch (value) {
   case true:
     turnLightOn();
     break;
   case false:
     turnLightOff();
     break;
   default:
     console.log(`I'm afraid I can't do that.`);
 }
}
```

Seria possível alcançar o log no último ramo do `switch`? Se em runtime o type de `boolean` for igual ao declarado, não, porém, os tipos em runtime podem não ser iguais aos tipos declarados, se, por exemplo, um usuário chamar a função com um `value` do tipo `string` o último ramo será sim alcançado.

O comportamento do código se torna obscuro e o próprio TypeScript se torna confuso quando existe essa divergência entre os types na declaração e os types em runtime por isso, esse tipos, ditos "inseguros" devem ser evitados sempre que possível.
# Você não pode fazer overload de um método usando os types do TS
Linguagens como C++ e Java permitem definir múltiplas versões de uma função variando sua assinatura, isso é, versões que diferem apenas nos tipos dos parâmetros, o que é chamado de "overload" ou "sobrecarga" de métodos, isso não é possível no TS.

```ts
function add(a: number, b: number): number {
  // Erro: Duplicate function implementation.
  return a + b;
}

function add(a: string, b: string): string {
  // Erro: Duplicate function implementation.
  return a + b;
}
```

Na verdade o TS até fornece uma feature nesse sentido, mas que atua, devido a já citada independência do type checking e do transpiling, apenas dentro do escopo de tipos, e não permite diferenciar a implementação das funções, apenas tipar as assinaturas:

```ts
function add(a: number, b: number): number;
function add(a: string, b: string): string;
function add(a: any, b: any): any {
    return a + b;
}
```

Basicamente esse snippet diz: "Se forem fornecidos dois números a saída será um número, mas se forem fornecidas duas `strings` a saída será uma string".
# Os tipos do TS não tem efeito sobre a performance do código em runtime
Uma última consequência é que não há nenhum efeito do TypeScript sobre a eficácia do código em runtime, isto é, os tipos TS não tem nenhum custo de performance, lembre-se, o que roda efetivamente é o código JS, sem tipos, de interfaces, obtido através do transpiling do TypeScript, há entretanto duas ressalvas:

1. Apesar de não apresentar overhead de execução em runtime, existe um overhead de compilação, um tempo de building a mais
2. Se o código estiver sendo emitido para uma versão antiga da especificação alguns recursos talvez tenham que ser emulados o que apresenta, por vezes, uma certa ineficácia comparada com a implementação nativa