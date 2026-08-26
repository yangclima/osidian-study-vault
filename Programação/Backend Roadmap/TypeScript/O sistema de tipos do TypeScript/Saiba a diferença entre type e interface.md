Sempre que você precisa declarar o type nomeado no TS você se depara com duas opções: Usar `type` ou `interface`. A linha entre essas duas sintaxes é muito e tem se tornado cada vez mais tênue, tanto que, na maioria das situações, não faz diferença usar um ou outro, a regra é então ser consistente no uso de um deles, isto é, adotar algum tipo de convenção e saber como escrever os mesmos tipos usando cada um deles para que você seja capaz de ler código independente da convenção.

Se você estiver começando uma nova codebase e precisa adotar um estilo, a recomendação oficial é usar `interface` sempre que possível e `type` sempre que necessário mas, em alguns casos, podemos forçar o uso do `type` para ter uma sintaxe mais simples e clara.

> Hoje, já que é desnecessário, é considerada uma má prática de código adicionar `I` no início do nome das interfaces

Em geral, há muitas similaridades entre as sintaxes, podemos usar assinatura de índice com ambas, ambas tem [[Saiba distinguir entre Type Checking e Excess Property Checking|Type Checking e Excess Property Checking]], ambas podem ser usadas para definir tipos de funções (Apesar da sintaxe ficar mais clara com `type`), ambas suportam generics e, fora algumas exceções, uma `interface` pode estender um `type` assim como um `type` pode expandir uma `interface`.

Quanto a um estender o outro, a exceção é que uma `interface` só é capaz de estender um `type` que poderia ser declarado como `interface`, isto é, não pode estender um union, tuple ou array type, por exemplo, enquanto o ``type`` pode expandir qualquer tipo usando `&`.

Uma outra diferença é que `interface` com `extends` fornece uma checagem ligeiramente mais profunda que `type` com `&`, apontando quando um tipo estende incorretamente outro gerando um tipo impossível.

A ``interface`` também apresenta um comportamento distinto conhecido como `declaration merging`. Basicamente, podemos declarar diversas vezes uma interface no mesmo módulo e essas declarações serão automaticamente mescladas de modo que as propriedades de cada declaração serão integradas resultando numa só mais geral, esse comportamento é útil em casos de uso mais complexos. 

Uma outra distinção é que o TS sempre se refere a uma interface usando seu nome enquanto tem maior liberdade para substituir um type pela sua definição o que costuma gerar mensagens de erros mais expressivas e completas quando usamos interface ao invés de type, isso faz alguma diferença quando usamos `declaration: true` no nosso [[Saiba que configuração do TypeScript você está usando|arquivo de configuração]]. 

Por fim, como já falado, a regra que dica é: Se já existe uma convenção na codebase, adote-a, caso não exista, prefira usar interfaces e use types quando for preciso ou for mais ergonômico.

Usando a rule `consistent-type-definitions` do [[Dia 31|ESLINT]] você pode garantir a consistência no uso das sintaxes.

	