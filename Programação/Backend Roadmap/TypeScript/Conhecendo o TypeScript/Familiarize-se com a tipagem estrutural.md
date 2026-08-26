Como vimos no artigo [[TypeScript para Programadores JavaScript]], o TS usa um modelo chamado Structural Type System, também chamado de Duck Typing ("If it walks like a duck and talks like a duck, then it probably is a duck.”) que significa, na prática, que a sua verificação de tipos se baseia nas propriedades dos objetos, se você passa um objeto que tem as propriedades compatíveis com tipo declarado, a checagem passa, independente da origem desse objeto. Entretanto, esse comportamento pode, em alguns casos, levar a erros e confusões.

A principal fonte de erros associados a essa tipagem advém de casos onde criamos uma função para operar um determinado tipo mas, sem querer, passamos a usá-la para operar sobre uma extensão desse tipo de modo que a implementação passa a ser um caso de uso errado e nenhum erro será mostrado, já que na prática, as restrições de tipo estão sendo obedecidas, por exemplo:

```ts
interface Vector2D {x: number; y: number;}
interface Vector3D {x: number; y: number; z: number;}

function calculateLength(v: Vector2D): number {
  return Math.sqrt(v.x ** 2 + v.y ** 2);
}

function normalize(v: Vector3D): Vector3D {
    const length = calculateLength(v);
    return {
       x: v.x / length,
       y: v.y / length,
       z: v.z / length,
    }
}
```

Veja que não há erros de tipagem, apesar disso, `calculateLength` não calcula corretamente o comprimento do `Vector3D` e também não mostra nenhum tipo de erro, afinal, todas as propriedades do tipo `Vector2D` que é declaradamente o tipo de dado que a função é feita para operar existem dentro de `Vector3D` mesmo que eu não declare explicitamente no código que esse vetor 3d estende o 2d. 

Ao escrever funções nós costumamos imaginar que elas serão chamadas com argumentos que possuem estritamente as propriedades dos tipos que declaramos e nenhuma outra, o que é conhecido como tipo "fechado", "selado" ou "preciso" mas que não pode ser expressado no sistema de tipos do TS, que só possui tipos "abertos".

isso traz algumas consequências, veja o seguinte exemplo:

```ts
function calculateLengthL1(v: Vector3D) {
  let length = 0;
  for (const axis of Object.keys(v)) {
    const coord = v[axis];
    // Erro: Element implicitly has an 'any' type because 'string' can't be 
    //       used to index type 'Vector3D'
    length += Math.abs(coord);
  }
  return length; 
}
```

A primeira vista parece que o TS errou ao mostrar esse erro, mas pense: Se os tipos são abertos e portanto eu só garanto que os objetos tenham um certo conjunto de propriedades mas não que ele SÓ possui aquelas propriedades, por que o TS deveria presumir que `Object.keys(v)` irá conter so as propriedades `x`, `y` e `z`? No fim das contas, o TS foi muito sensato em sua atuação aqui.

Uma outra surpresa pode ocorrer ao trabalhar com classes, muitas vezes construímos esse objetos com alguma lógica de restrição e validação no construtor, partindo disso, podemos construir funções com tipos que se referem a essas classes assumindo a existência da lógica de validação, entretanto o Duck Typing só irá exigir que uma determinada propriedade existe nos argumentos passados e não que ela obedece alguma restrição predefinida. Por exemplo:

```ts
class SmallNumContainer {
  num: number;
  
  constructor(num: number) {
    if (num < 0 || num >= 10) {
      throw new Error(`You gave me ${num} but I want something 0-9.`)
    }
      this.num = num;
    }
}

const a = new SmallNumContainer(5);
const b: SmallNumContainer = { num: 2024 }; // Sem problemas
```

Apesar desses problemas, essa tipagem pode ser útil em alguns casos, sobretudo no que tange ingestão de dependências em testes unitários, por exemplo, imagine que você quer construir um teste unitário para a seguinte função:

```ts
interface User {
  id: int;
  username: string;
  email: string;
}

function getUsers(database: PostgresDB): User[] {
  const userRows = database.query('SELECT id, username, email FROM users;');
  return userRows.map(row => ({id: row[0], username: row[1], email: row[2]}));
}
```

Provavelmente você precisaria de uma biblioteca externa para mockar a sua database `PostgresDB`, aqui, entretanto, você pode usar o Duck Typing para criar uma versão mais enxuta do tipo `PostgresDB` apenas com os métodos que você precisa fazendo com que você consiga realizar o mock desse DB sem precisar entender os detalhes de implementação de `PostgresDB` temos então:

```ts
interface DB {
  query: (sql: string) => any[];
}

function getUsers(database: DB): User[] {
  const userRows = database.query('SELECT id, username, email FROM users;');
  return userRows.map(row => ({id: row[0], username: row[1], email: row[2]}));
}
```

E o teste unitário seria simplesmente:

```ts
test('getUsers', () => {
  const users = getUsers({
    query(sql: string) {
      return [
        [1, 'Morrison', 'mor@gmail.com'], 
        [2, 'Angelou', 'ang@gmail.com']
      ];
    }
  });
 
  expect(authors).toEqual([
    {id: 1, username: 'Morrison', email: 'mor@gmail.com'},
    {id: 2, username: 'Angelou', email: 'ang@gmail.com}
  ]);
});
```

O trunfo aqui é inclusive ser capaz de posteriormente trocar a lib do banco de dados ou o sistema sem substituir os tipos aqui, já que usando a interface `DB` nós só exigimos que exista o método query e isso nos permite escrever no exemplo acima um função de mock extremamente simples.