Quando tentamos atribuir um objeto literal para uma variável que tem um tipo declarado o TS realiza o que chamamos de `Excess Peoperty Checking` que verifica e proíbe a atribuição de objetos literais que possuam propriedades extras, isto é, propriedades que não estão declaradas na interface do tipo, o objetivo desse comportamento é evitar erros muito comuns presentes quando temos propriedades opcionais declaradas na interface do tipo, por exemplo, se temos uma propriedade `darkmode?: boolean` mas tentamos atribuir um literal com `darkMode = true` o erro acusado será de excesso de propriedades, como sabemos, o objetivo do Type Script é tanto evitar erros em runtime quanto evitar que você faça coisas sem intenção.

Vale ressaltar que esse comportamento não ocorre quando atribuímos o objeto literal  primeiro a uma variável intermediária e depois a variável com tipo declarado, já que aí entra o conceito de [[Familiarize-se com a tipagem estrutural|tipagem estrutural]] e o funcionamento dos [[Pense nos tipos como conjuntos de valores|tipos como conjuntos de valores]], isso também não ocorre quando usamos [[Prefira Type Annotations a Type Assertions|type assertions]], mais um motivo para evitá-las.

Uma outra forma de evitar esse comportamento é adicionar um index signature:

```ts
interface Options {
 darkMode?: boolean;
 [otherOptions: string]: unknown; // Essa propriedade
}
```

O grande conflito aqui é que esse comportamento acaba conflitando com a tipagem estrutural o que pode gerar problemas para interpretar de maneira intuitiva a linguagem e suas declarações, para amenizar isso devemos pensar no Type Checking o no Excess Property Checking como dois processos distintos, o primeiro sendo o comportamento padrão e o segundo ocorrendo só para atribuições de objetos literais para evitar erros de intenção.

Uma outra checagem desse tipo no TS ocorre nos chamados Weak Types, tipos fracos, conceito interno do TS para interfaces de tipo que declaram apenas propriedades opcionais, nesse caso, seja atribuindo diretamente através de um literal ou indiretamente a checagem se aplica e obriga que pelo menos uma propriedade da interface definida.