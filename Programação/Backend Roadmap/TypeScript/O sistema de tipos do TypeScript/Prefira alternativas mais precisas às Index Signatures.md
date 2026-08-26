Numa declaração como `type TypeName = {[property: string]: string}`, `[property: string]: string` é uma index signature e define Uma nome para as chaves (`property`), um tipo para as chaves (`string`) que deve ser um [[Pense nos tipos como conjuntos de valores|subconjunto]] de `string | number | symbol`  e um tipo para os valores (`string`) que pode ser qualquer um.

Em geral as `Index Signatures` tem diversas desvantagens com relação a tipos mais precisamente definidos, elas desativam o [[Saiba distinguir entre Type Checking e Excess Property Checking|excess property checking]] e outras barreiras contra erros de digitação, tornam a sua [[Use o seu editor para interrogar e explorar o sistema de tipos|IDE]] incapaz de prover os principais serviços de linguagem como autocomplete e muitas outras desvantagens por isso, devemos evitar sempre que pudermos a sua utilização.

Historicamente, seu principal caso (justo) de uso é quando temos dados em formatos realmente imprevisíveis ou desestruturados, por exemplo uma função de parsing de um CSV, entretanto, ainda assim, hoje temos alternativas melhores para isso, como o tipo `Map`, advindo da classe [[JavaScript Map]] também chamado de array associativo, por exemplo `type TypeName = {[property: string]: string}` equivale a `type TypeName = Map<string, string>`, o `Map` se sobressai por oferecer métodos para um possível parsing que levará a um tipo mais estrito.

No caso do tipo a ser modelado pertencer a um conjunto estrito de possíveis campos, é melhor modelá-lo com unions ou propriedades opcionais do que com index signatures:

```ts
interface Row1 { [column: string]: number } // Ruim
interface Row2 { a: number; b?: number; c?: number; d?: number } // Bom
type Row3 =
 | { a: number; }
 | { a: number; b: number; }
 | { a: number; b: number; c: number; }
 | { a: number; b: number; c: number; d: number }; // Ótimo, mas complicado
```

Ao invés de usar uma index signatures podemos usar o utility type `Record<Keys, Types>`, por exemplo:

```ts
type Vector3D = Record<'x' | 'y' | 'z', number>
```

No entanto, uma possibilidade onde se justifica o uso das index signatures é quando queremos desativar o excess property checking quando queremos permitir outras chaves quaisquer num objeto, por exemplo:

```ts
interface ButtonProps {
  title: string;
  onClick: () => void;
  [otherProps: string]: unknown;
}
```

Nesse caso, o TS exige a correspondência de `title` e `onClick` com seus tipos definidos e exige que essas propriedades existem mas deixa livre a possibilidade de adicionar novas propriedades quaisquer.

A lição que fica é então evitar sempre a utilização de index signatures e utilizar ao invés disso as opções fornecidas, como mapped types,  interfaces, types, `Map`, `Records` ou as index signatures com espaços de chave mais restritos.
