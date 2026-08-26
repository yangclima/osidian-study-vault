O processo de refinamento de tipos que temos no Typescript, isto é, o processo por meio do qual o TS consegue inferir um tipo mais específico para uma variável definida com um tipo mais abrangente ao longo do código é chamado de Type Narrowing e está associado com o curioso fato de que, no TS, diferente de outras linguagens o tipo associado a uma variável está depende da parte do código onde estamos analisando no que chamamos de Análise do Fluxo de Controle.

Isso quer dizer que num código como:

```ts
const elem = document.getElementById('what-time-is-it');
// Tipo inferido: const elem: HTMLElement | null

if (elem) {
 elem.innerHTML = 'Party Time'.blink();
 // Tipo inferido: const elem: HTMLElement
} else {
 elem
 // Tipo inferido: const elem: null
 alert('No element #what-time-is-it');
}

```

Como podemos ver, o tipo que o TS infere para `elem` depende da parte do código que estamos tratando, o que mostra o poder de inferência da linguagem e justifica o motivo de dizermos que "No TypeScript, um símbolo tem um tipo em uma localização".

Existe diversas formas ed manipular o Type Narrowing, por exemplo, através de um statement ``return`` ou ``throw``:

```ts
const elem = document.getElementById('what-time-is-it');
// Tipo inferido: const elem: HTMLElement | null

if (!elem) throw new Error('Unable to find #what-time-is-it');

elem.innerHTML = 'Party Time'.blink();
// Tipo inferido: const elem: HTMLElement
```

Uma outra opção é usar um estrutura condicional com `instanceof`:

```ts
function contains(text: string, search: string | RegExp) {
  if (search instanceof RegExp) {
    return !!search.exec(text);
    // Tipo inferido: (parameter) search: RegExp
  }
 
  return text.includes(search);
  // ^? (parameter) search: string
}
```

Podemos ainda distinguir tipos usando a presença de uma propriedade, fazemos isso usando  uma checagem de `property in object`:

```ts
interface Apple { isGoodForBaking: boolean; }
interface Orange { numSlices: number; }

function pickFruit(fruit: Apple | Orange) {
  if ('isGoodForBaking' in fruit) {
    fruit
    // Tipo inferido: (parameter) fruit: Apple
  } else {
    fruit
    // Tipo inferido: (parameter) fruit: Orange
  }
  
  fruit
  // Tipo inferido: (parameter) fruit: Apple | Orange
}
```

Além disso, algumas funções built-in podem realizar o narrowing:

```ts
function contains(text: string, terms: string | string[]) {
 const termList = Array.isArray(terms) ? terms : [terms];
 // Tipo inferido: const termList: string[]
 // ...
}
```

As tagged unions são uma forma bastante útil de fazer essa distinção de tipos usando a checagem do valor de uma propriedade, por exemplo:

```ts
interface UploadEvent { type: 'upload'; filename: string; contents: string }
interface DownloadEvent { type: 'download'; filename: string; }
type AppEvent = UploadEvent | DownloadEvent;

function handleEvent(e: AppEvent) {
  switch (e.type) {
     case 'download':
       console.log('Download', e.filename);
       // Tipo inferido: (parameter) e: DownloadEvent
       break;
     case 'upload':
       console.log('Upload', e.filename, e.contents.length, 'bytes');
       // Tipo inferido: (parameter) e: UploadEvent
       break;
  }
}
```

Em geral, você deve pensar 20 vezes antes de usar uma type assertion para contrariar a análise do fluxo de controle feita pelo TS, ele é muito bom fazendo isso e na maioria das vezes que ele apontar um erro, de fato há um erro.

O TS também oferece a possibilidade de que você crie funções capazes de auxiliar no type narrowing, nos chamados **User-defined type guards**, por exemplo:

```ts
function isInputElement(el: Element): el is HTMLInputElement {
  return 'value' in el;
}

function getElementContent(el: HTMLElement) {
  if (isInputElement(el)) {
    return el.value;
    // Tipo inferido: (parameter) el: HTMLInputElement
  }
  
  return el.textContent;
  // Tipo inferido: (parameter) el: HTMLElement
}
```

Nesse caso, `el is HTMLInputElement` é chamado de type predicate e basicamente diz para o TS: "Se o retorno dessa função for `true` você pode realizar o narrow o tipo para `HTMLInputElement`". Seja cuidadoso ao utilizar essa feature, não há nenhum tipo de checagem sobre o conteúdo interno da função, por isso, não há muita diferença entre uma função desse tipo e uma asserção de tipo.

Um padrão muito comum é checar se uma determinada variável é ``undefined``, por exemplo:

```ts
const nickname = nameToNickname.get(yourName);
let nameToUse: string;

if (nickname !== undefined) {
  nameToUse = nickname;
} else {
  nameToUse = yourName;
}
```

Por ser tão comum, foi criado o operador chamado "nullish coalescing operator" `??` que basicamente reduz esse snippet para:

```ts
const nameToUse = nameToNickname.get(yourName) ?? yourName;
```

Entender como o narrowing ocorre te ajuda a construir uma intuição sobre como a inferência ocorre e como evitar certos tipos de erros de uma forma "type safe".