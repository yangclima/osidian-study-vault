O TypeScript é um caso muito especial de linguagem que não é nem executada por um interpretador como é ocaso do *JavaScript* ou do *Ruby* e nem compilada para uma linguagem de baixo nível como é o caso do *C* ou do *[[Java]]*, ao invés disso, ela é compilada para uma outra linguagem de alto nível, o JavaScript, e é esse JavaScript que é executado, não o seu código TypeScript, e justamente por isso é tão importante entender a relação entre essas duas linguagens.

A primeira ideia para ter em mente é que o TypeScript é um Superconjunto do JavaScript, isto é, todo programa JavaScript é, sintaticamente, um programa TypeScript, já o contrário não é necessariamente verdade já que o TS traz uma sintaxe adicional para permitir a especificação de tipos. Esse fato é especialmente útil quando precisamos migrar uma codebase JS para o TS.

```ts
function greet(who: string) {
 console.log('Hello', who);
}
```

O código acima contém um exemplo de sintaxe adicionada pelo TS, o `: string` é um type annotation específico do TypeScript e ao usá-lo você sai do âmbito do JavaScript.

Apesar da existência dessa sintaxe, o TS traz muito mais valor aos programas JavaScript do que simplesmente uma forma de especificar tipos, além disso, mesmo que nós não usemos essa sintaxe adicional, continua sendo muito útil trabalhar com TypeScript, por exemplo:

```ts
let city = 'new york city';
console.log(city.toUppercase());
```

Mesmo que nesse snippet não estejamos usando absolutamente nada da sintaxe extra do TypeScript, ele será capaz de apontar o seguinte problema no nosso código:

```
Property 'toUppercase' does not exist on type 'string'. Did you mean 'toUpperCase'?
```

Essa capacidade do TS de detectar automaticamente os tipos no nosso código é chamada de [[TypeScript para Programadores JavaScript#Tipos por inferência|Inferência de tipos]], uma parte chave do TypeScript que, nesse caso, permitiu que, mesmo sem que nós precisemos escrever um caractere sequer, ele tenha conseguido detectar um erro no nosso código e ainda sugerir uma solução.

Apesar dessa capacidade de inferência, temos muito a ganhar declarando os tipos no nosso código, isso ocorre por que fazendo essa declaração nos comunicamos nossa **intenção** para o TypeScript permitindo que ele detecte pontos no nosso código que não são compatíveis com essa intenção, não se trata de sintaxe mas de lógica de alto nível, podemos então tomar como lei que **Quanto mais informação você fornece ao TypeScript mais problema ele é capaz de resolver**.

Um dos principais objetivos do sistema de tipos do TypeScript é detectar erros que viriam a ocorrer em runtime mesmo sem executar o programa, por esse motivo esse sistema é dito um **Sistema Estático de Tipos**.

Ademais, existem alguns casos onde mesmo que o código não lance essas exceptions em runtime, isto é, executem sem problemas como código JavaScript, o type checker atue apontando problemas no código, esse é o caso que ocorre quando tentamos acessar propriedades que não existem nos objetos, o TS lança um erro dizendo que a propriedade não existe enquanto o JS simplesmente retornaria silenciosamente `undefined`. O mesmo ocorre para algumas operações de soma entre tipos diferentes que tem um comportamento válido mas esquisito no JS mas que no TS são apontadas como erro, ou quando passamos o número errado de argumentos para uma função.

```ts
console.log({id: 1}.name) // Exibe "undefined" no JS
// Erro: property 'name' does not exist on type '{ id: number; }'

const a = null + 7; // Resulta em 7 no JS
// Erro: The value 'null' cannot be used here.

const b = [] + 12; // Resulta em '12' no JS
// Erro: Operator '+' cannot be applied to types ...

alert('Hello', 'TypeScript'); // Alerta "Hello"
// Erro: Expected 0-1 arguments, but got 2
```

Essa ideia contraria uma das guidelines do sistema de tipos do TypeScript que diz ele é deveria modelar o comportamento em runtime do JavaScript, o ponto é que nesse caso o TS considera que os exemplos citados acima são provavelmente um erro ao invés de um caso de uso proposital do desenvolvedor, no fim das contas estamos entrando numa questão de gosto, isso significa que adotando o TypeScript você, quer queira, quer não, está confiando um pouco no julgamento dos desenvolvedores da linguagem.

Uma outra divergência com relação a sistemas de tipos de outras linguagens também advém do comportamento do JS, algumas linguagens apontariam erros no seguinte snippet:

```ts
const x = 2 + '3';
const y = '2' + 3;
```

Mas o TS não o faz, já que nesse caso ele realmente modela o comportamento em runtime do JS, que não apresentaria problemas de execução nessas linhas, mesmo que isso seja questionável.

Por fim, existem ainda casos onde problemas de runtime ocorrem mesmo que o sistema estático de tipos não encontre problemas, isso é comum ao usar o tipo `any` e em outros caso, a causa principal desses problemas está relacionada com o fato de eventualmente o tipo e valor de uma variável em runtime ser capaz de divergir do seu tipo estático, isto é, o TS não é capaz de garantir a acurácia de seus tipos estáticos (Não é uma linguagem sólida ou `sound`)

