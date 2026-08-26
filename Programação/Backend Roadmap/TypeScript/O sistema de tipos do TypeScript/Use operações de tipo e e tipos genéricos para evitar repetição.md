O princípio DRY (Don't Repeat Yourself) já é tipo como uma verdade absoluta no escopo de valores de qualquer linguagem e tido como uma boa prática de desenvolvimento, isto é, sempre ter em mente a ideia de evitar código repetitivo usando para isso as abstrações existentes (funções, classes, loops, variáveis...). Esse princípio deve ser aplicado também no [[Saiba identificar se um símbolo pertence ao espaço de valores ou de tipo|escopo de tipos]] para evitar os mesmos problemas e para isso precisamos conhecer os recursos disponíveis para isso.

O primeiro ponto e o mais comum é **nomear os tipos**, para evitar diretamente a repetição:

```ts
// Substitua
function distance(
  a: { x: number; y: number }, 
  b: { x: number; y: number }
) { /* ... */ }

// Por 
interface Point {
  x: number;
  y: number;
}

function distance(a: Point, b: Point) { /* ... */ }
```

O segundo ponto é: Se muitas funções possuem a mesma assinatura de tipos, ao invés de repetir essa assinatura, crie um tipo para ela e [[Aplique tipos a expressões inteiras de funções quando possível|aplique às funções]].

```ts
// Substitua
async function get(url: string, opts: Options): 
Promise<Response> { /* ... */ }

async function post(url: string, opts: Options): Promise<Response> { /* ... */ }

// Por 
type HTTPFunction = (url: string, opts: Options) => Promise<Response>;

const get: HTTPFunction = (url, opts) { /* ... */ }
const post: HTTPFunction = (url, opts) { /* ... */ }
```

O terceiro ponto é, **quando os tipos tiverem o mesmo significado, representarem o mesmo objeto, ao invés de repetir o nome de propriedades usar operações de tipos**:

```ts
// Substitua 
interface User {
  name: string;
  age: number;
  cpf: string;
}

interface UserWithRole {
  name: string;
  age: number;
  cpf: string;
  role: string;
}

// Por 
interface User {
  name: string;
  age: number;
  cpf: string;
}

interface UserWithRole extends User {
  role: string;
}
```

O quarto ponto é que s**e, mesmo apresentando significados diferentes, dois tipos forem correlacionados você pode extrair subconjuntos de seus tipos em um terceiro tipo "ancestral"**:

```ts
// Substitua 
interface Bird {
 wingspanCm: number;
 weightGrams: number;
 color: string;
 isNocturnal: boolean;
}

interface Mammal {
 weightGrams: number;
 color: string;
 isNocturnal: boolean;
 eatsGardenPlants: boolean;
}

// Por
interface Vertebrate {
 weightGrams: number;
 color: string;
 isNocturnal: boolean;
}

interface Bird extends Vertebrate {
 wingspanCm: number;
}

interface Mammal extends Vertebrate {
 eatsGardenPlants: boolean;
}
```

No quinto ponto, **se um tipo deve "herdar" um subconjunto das propriedades de outro use indexação de propriedades:**

```ts
interface State {
 userId: string;
 pageTitle: string;
 recentFiles: string[];
 pageContents: string;
}

// Substitua
interface TopNavState {
 userId: string;
 pageTitle: string;
 recentFiles: string[];
}

// Por
interface TopNavState {
 userId: State['userId'];
 pageTitle: State['pageTitle'];
 recentFiles: State['recentFiles'];
};

// Ou, de forma mais simples, usando mapped types
type TopNavState = {
 [K in 'userId' | 'pageTitle' | 'recentFiles']: State[K]
};

```

Essa última forma (mapped types) é tão comum que a biblioteca padrão inclui uma facilidade nesse sentido, um tipo com generic chamado `Pick`:

```ts
type TopNavState = 
  Pick<State, 'userId' | 'pageTitle' | 'recentFiles'>
```

No sexto ponto, se você for usar o pattern de tagged unions, para evitar repetição você pode extrair um tipo para a tag ao invés de deixá-lo hard-coded:

```ts
interface SaveAction {
 type: 'save';
 // ...
}
interface LoadAction {
 type: 'load';
 // ...
}

type Action = SaveAction | LoadAction;

// Substitua
type ActionType = 'save' | 'load'; 

// Por
type ActionType = Action['type'];

```

No sétimo ponto, **se uma classe for criada podendo ser inicializada e depois atualizada, devemos evitar a repetição dos tipos do construtor**:

```ts
interface Options {
 width: number;
 height: number;
 color: string;
 label: string;
}

// Substitua
interface OptionsUpdate {
 width?: number;
 height?: number;
 color?: string;
 label?: string;
}

// Por
type OptionsUpdate = {[k in keyof Options]?: Options[k]};

// Ou, usando a facilidade `Partial` da biblioteca padrão
type OptionsUpdate = Partial<Options>
```

Para inverter as chaves e valores de um tipo, podemos usar:

```ts
interface ShortToLong {
 q: 'search';
 n: 'numberOfResults';
}
type LongToShort = { [k in keyof ShortToLong as ShortToLong[k]]: k };
// ^? type LongToShort = { search: "q"; numberOfResults: "n"; }
```

É importante, nesse contexto,  ter em mente um conceito do TS chamado de Tipos Mapeados Homomórficos que basicamente se refere a preservação de modificadores como `readonly` e `?` (Optional) ao mapear tipos com alguma variação de `K in keyof T`. O mesmo ocorre quando usamos `Pick`, isto é, se tivermos, por exemplo `interface User { readonly name: string, age?: number}` teremos `Pick<User,name>` sendo equivalente a `{ readonly name: string}` e  `Pick<User,age>` equivalente a `{age?: number}` enquanto para, por exemplo `{age: User[age]}` (Tipo mapeado não homomórfico) é equivalente a `{age: number}` (Sem o optional) esse tipo de mapeamento também preserva as strings de documentação do TS.

Normalmente é melhor criar primeiro os tipos e depois aplicá-los às variáveis, contudo, em alguns casos como algum tipo de Schema ou especificação de API, podemos tomar um objeto como fonte da verdade e utilizá-lo como base para um tipo:

```ts
const INIT_OPTIONS = {
 width: 640,
 height: 480,
 color: '#00FF00',
 label: 'VGA',
};

// Substitua isso
interface Options {
 width: number;
 height: number;
 color: string;
 label: string;
}

// Por
type Options = typeof INIT_OPTIONS;
```

Nesse mesmo sentido, podemos precisar ocasionalmente criar um tipo com base no retorno de uma determinada função, para isso temos uma facilidade chamada `ReturnType` na biblioteca padrão:

```ts
type UserInfo = ReturnType<typeof getUserInfo>;
```