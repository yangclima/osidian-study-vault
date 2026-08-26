É muito comum, quando você é iniciante no TS sentir a necessidade de tipar absolutamente tudo no seu código, entretanto, isso não é necessário, não é a proposta da linguagem e só deixa seu código mais sujo, mais difícil de ler e diminui sua produtividade escrevendo. O TypeScript tem uma inferência de tipos extremamente poderosa que será sua aliada na codificação e te permitirá usufruir do sistema de tipos sem usar milhares de type annotations.

Mesmo para objetos complexos o TS é capaz de realizar inferência então evite definir os seus tipos, em geral, use tipagem quando o tipo que você deseja que um objeto tenha for diferente do tipo que o TS está inferindo para ele.

Para objetos literais, no entanto, o tipo também se justifica quando você quer usufruir de serviços de linguagem como [[Saiba distinguir entre Type Checking e Excess Property Checking|excess property checking]] ou garantir que os erros sejam reportados na declaração do objeto ao invés de 10 camadas de abstração acima onde o objeto é importado e utilizado.

O uso de tipos também se justifica quando o TS não tem contexto o suficiente para inferi-los, por exemplo, nos parâmetros de funções (Exceto para parâmetros com valor padrão ou para funções declaradas como callback para uma biblioteca com declarações de tipo), estes, por sua vez, guiam o código escrito dentro do corpo da função de modo que quase nunca precisaremos declarar tipos parar as variáveis criadas nele.

Quanto ao tipo de retorno da função, na maioria das vezes os TS será capaz de inferir uma tipagem com base na clause de retorno porém, se uma função tem múltiplas declarações `return`, é parte de uma API pública ou deve retornar um tipo nomeado, você pode e às vezes deve declarar um tipo para o seu retorno.

A regra `no-inferrable-types` do TS pode ajudar a evitar type annotations desnecessárias.

