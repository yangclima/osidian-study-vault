O TS, diferente da maioria das outras linguagens também é capaz de inferir tipos a partir do contexto no qual um valor é definido e é importante entender esse comportamento para evitar erros relacionados bem como aproveitar dessa capacidade. Veja o seguinte exemplo:

```ts
type Language = "ts" | "js" | "java";
function setLanguage(lang: Language) { /* ... */ }

setLanguage("ts"); // OK


let lang = "ts"; 
setLanguage(lang);
// Erro: Argument of type 'string' is not assignable to parameter of type 'Language'.
```

Na primeira chamada de `setLanguage` o TS infere que `"ts"` é compatível com o tipo `Language` a partir do contexto onde o valor é declarado, por outro lado, quando definimos a variável `lang`o TS não tem contexto e por isso [[Entenda como o tipo de uma variável é inferido|classifica a variável]] como `string`, em seguida, ao passar `lang` como argumento da função ele compara não mais o valor mas o tipo de `lang`, apontando um erro por que ele não é compatível com o tipo `Language`.

Ao lidar com valores primitivos é simples resolver isso, uma opção é adicionar um type annotation declarando o tipo da variável, a segunda é declarar a variável como `const` ao invés de `let`, permitindo que o TS defina um tipo mais estrito para `lang`, nesse caso, em geral, usamos const se não há necessidade de alterar o valor da variável e uma type annotation se houver essa necessidade.

Para objetos, tuplas e arrays o problema é um pouco mais complicado, já que simplesmente os definir com `const` não faz com que o TS os infira seu tipo como tal, assim, nesse caso, os grandes aliados serão as type annotations, a asserção `as const`, o operador `satisfies` ou em último caso as type assertions.

Um outro caso em que o TS atua muito bem extraindo o tipo de uma variável a partir do contexto é para funções passadas como callback, a TS consegue inferir a partir do tipo de função especificado na assinatura da função para a qual o callback está sendo passado os tipos de cada um dos argumentos e retorno para a função de callback.