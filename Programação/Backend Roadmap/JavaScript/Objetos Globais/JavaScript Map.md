Um `Map` é similar a um `Object` normal, ambos permitem que valores sejam atribuídos a chaves, retornar esses valores, remover as chaves, e detectar se algo está armazenado numa chave. tanto que `Objetc` tem sido usado como `Map` historicamente. Existem entretanto as diferenças:

1. O `Map` não contém nenhuma chave por padrão. Ele só contém o que é definido explicitamente nele enquanto `Object` possui por padrão um prototype, o que pode levar a conflitos ao definir as chaves
2. As chaves do `Map` podem ser de qualquer tipo, enquanto as do `Object` devem ser do tipo `string`, `number` ou `symbol`.
3. As chaves dentro do `Map` são ordenadas de forma simples, de maneira direta na ordem em que foram inseridas enquanto o `Object` tem uma ordem complexa de ordenação.
4. O número de items dentro de um `Map` é facilmente retornado pela propriedade `size` enquanto você deve determinar manualmente a quantidade de chaves de um `Object`.
5. Um `Map` pode ser diretamente iterável enquanto um `Object` não tem um protocolo de iteração definido
6. O `Map` performa melhor em cenários envolvendo adições e remoções frequentes em pares chave-valor.
7. O `Map` não tem suporte nativo para a serialização ou análise sintática para transformá-lo, por exemplo, em um objeto JSON.

Para criar um `Map`:

```js
const mapName = new Map();
```

Para adicionar um par chave valor:

```js
mapName.set(chave, valor)
```

Para pegar o valor associado a uma chave:

```js
mapName.get(chave)
```

Para verificar se existe um valor associados a uma chave:

```js
mapName.has(chave)
```

Para deletar uma chave:

```js
mapName.delete(chave)
```

Para deletar todas as chaves:

```js
mapName.clear()
```

Para verificar a quantidade de pares chave valor de um map:

```js
const pairQuantity = mapName.size
```

Para iterar sobre um `Map`:

```js
for(const [key, value] of mapName){
 /* ... */
}
```

Ou ainda:

```js
mapName.forEach((value, key) => { /* ... */ })
```

Para clonar um `Map`:

```js
const clone = new Map(mapName)
```

E para mesclar dois `Map`:

```js
const merged = new Map([...map1, ...map2])
```

