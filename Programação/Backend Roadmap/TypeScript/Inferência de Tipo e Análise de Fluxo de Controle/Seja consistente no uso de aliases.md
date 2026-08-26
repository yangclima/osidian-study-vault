Quando temos um objeto e depois mapeamos uma de suas propriedades, que tem como valor um outro objeto, para uma variável, como no exemplo:

```ts
const local = {name: 'home', coords: [-23.55, -46,63]}

const homeCoords = local.coords
```

Estamos criando um alias de modo que mudanças no valor ou propriedades da variável (O alias) serão visíveis no objeto original, modificarão seu valor. 

O ponto é que esses aliases complicam bastante a atuação do TS na análise de fluxo de controle ([[Entenda o type Narrowing|Type Narrowing]]), basicamente, a tipagem estática não consegue, na maioria dos casos, entender a relação entre um alias e o objeto a qual ele ser refere.

Apesar desses problemas, é muito inconveniente não usar os aliases, o código fica muito mais verboso e poluído por isso, a regra é que devemos ser consistentes no seu uso. Como um exemplo, o seguinte código

```ts
type coordinates = [number, number];
type local = { name?: string; coords: coordinates };
 
const homeLocal: local = { name: "home", coords: [-23.55, -46.63] };

function printLocal(local: local): void {
  const name = local.name;
  const [lat, long] = local.coords;

  if (local.name) {
    console.log(
      `Local: ${name.toUpperCase()}, Latitude: ${lat}, Longitude: ${long}`,
      // Erro: 'name' is possibly 'undefined'.
    );
  }
}
```

Note que, de fato, se `local.name` for não falsy, `name` também não será, mas o TS não consegue inferir isso, esse é um caso de inconsistência no uso de aliases, para sermos consistentes, verificaríamos `name` no if permitindo que o TS restrinja o tipo e evitando esse erro.

Uma dica nesse contexto é utilizar a desestruturação de tipos do TS, ao mesmo tempo que você garante uma nomeação consistente garante também uma declaração concisa, além disso, o refinamento de tipos ocorre melhor com variáveis locais que com propriedades de objetos.

Outro tópico complexo são funções que modificam os objetos, nesse caso, o TS assume que a funções modificam os objetos de modo consistente com seu tipo o que é, na verdade, muito otimista, por exemplo, o seguinte código não apresenta erros:

```ts
function printLocal(local: local): void {
  const name = local.name;
  const [lat, long] = local.coords;

  if (name) {
    setNameToNumber(local);
    console.log(
      `Local: ${name.toUpperCase()}, Latitude: ${lat}, Longitude: ${long}`,
    );
  }
}
```