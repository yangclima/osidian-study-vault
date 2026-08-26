No JS e TS, temos uma distinção entre uma definição de função e uma expressão de uma função:

```ts
// Definição
function fname(farg: fArgType): fReturnType {/* ... */}

// Expressão
const fname = function(farg: fArgType): fReturnType {/* ... */}

// Expressão 
const fname = (farg: fArgType): fReturnType => {/* ... */}
```

Em alguns casos a expressões apresentam uma certa vantagem à utilização das definições: Você pode aplicar Tipos á função inteira de uma vez ao invés de segmentar a tipagem, por exemplo:

```ts
type functionType = (fArg: fArgType) => fReturnType;
const fname: functionType = (fArg) => {/* ... */}
```

A partir disso o TS é capaz de inferir automaticamente o tipo dos argumentos, ao passar o mouse sobre `fArg` veremos `(parameter) fArg: fArgType`. Essa abordagem é muito útil quando temos várias funções com assinaturas semelhantes, que performam ações fundamentalmente parecidas e torna a lógica mais aparente e fica mais fácil e explícito checar o formato das funções.

É muito comum que algumas bibliotecas forneçam inclusive tipos para assinaturas de funções comuns ou callbacks recorrentes, por exemplo, o React disponibiliza o tipo `MouseEventHandler`.

Essa ideia também pode ser aplicada quando queremos que a assinatura de uma função seja igual a assinatura de uma outra, por exemplo quando queremos criar uma espécie de Wrapper que adequa o comportamento de uma função convenientemente, nesse caso, podemos usar:

```ts
const fname: typeof anotherFunction = (farg) => {/* ... */}
```

Também é possível usar a tipagem de parâmetros de uma outra função mas mudando o retorno da função. Para isso, usamos os rest parameters e o tipo utilitário `Parameters`:

```ts
function fName(
  ...args: Parameters<typeof anotherFunction>
): fReturnType {
  // ...
}
```

O TS consegue abstrair isso, mostrando no hover os parâmetros e tipos equivalentes aos de `anotherFunction`.

A dica que fica então é: Sempre que estiver repetidamente escrevendo tipos semelhantes para funções, mesmos tipos de argumento, mesmo retorno, centralize esse tipo, crie um tipo de função e aplique sobre expressões ao invés de declarações, além disso, se você estiver escrevendo um biblioteca, vale a pena disponibilizar tipos para as funções de callback mais comuns, contudo, não leve essa regra ao extremo, sempre pese o que é mais conveniente em cada caso.