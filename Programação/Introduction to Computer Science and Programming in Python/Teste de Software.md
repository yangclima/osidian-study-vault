---
tags:
  - Procedimento
---
> O **Teste de Software** é o processo de executar um programa para testar e garantir que ele funciona como pretendido.

O primeiro passo para testar o seu programa é livrá-lo dos erros de sintaxe e semântica estática, se você ainda não conseguiu passar desse ponto com uma linguagem de programação, você não está pronto para testar  o seu software.

É importante entender que os teste jamais serão capazes de te garantir com 100% de certeza que o seu código está livre de bugs, **seu objetivo, na verdade é o contrário: Permitir que você encontre o bugs, evidenciá-los**, tornar óbvio, ou pelo menos mais simples o processo de encontrar os problemas do seu sistema.

O segredo para o teste eficiente é encontrar o conjunto de entradas chamado de ***test suite ou test cases*** que possui a característica de ser o conjunto de inputs com a maior probabilidade de indicar um erro, caso ele exista. Se você for capaz de encontrar o melhor ***test suite*** possível para o seu código, ele poderá ser dito ***test completness***, porém, conforte-se com a ideia de que para funções grandes e complexas é impossível, para dizer o mínimo. 

É preciso destacar que o processo de teste de software é contínuo e deve acontecer juntamente com o desenvolvimento, e não após a conclusão, isso garante que cada parte individual do software seja testada quando o código ainda não é muito complexo e esse processo consequentemente seja mais simples. 

Para simplificar a compreensão do processo de criação de ***testes*** podemos dividi-lo em dois tipos:

# Black-Box Testing
Esse processo de criação de testes baseia-se numa ==análise da especificação== (o que o código deveria fazer) e não do código em si, seu propósito é evitar lacunas nos testes que estejam correlacionadas com os erros do próprio código. Imagine que um erro de lógica faça com que um programador tenha no seu código um  lacuna, um caso onde o funcionamento não ocorra como desejado, provavelmente ele deixará a mesma lacuna nos seus testes, afinal, ele não pensou nisso. Essa é a vantagem do ***Black-box testing***,  gerar um camada de independência que impeça que erros se propaguem do código para os testes, além disso, como ele baseia-se apenas na implementação o teste criado nesse princípio funcionaria independente das mudanças do código.  Um dos fatos mais importantes para ser levado em conta é que o teste deve testar não apenas entradas em condições favoráveis, mas também em ***condições limite***, para um lista, por exemplo, deveríamos testar  para uma lista vazia, um lista de exatamente um elemento e para uma lista de listas, além disso, para elementos de [[Mutabilidade e Imutabilidade|tipos mutáveis]] é essencial considerar o [[Aliasing]]

# Glass-Box Testing
Por mais que os testes baseados na especificação ou intenção de implementação sejam muito eficientes, é essencial que haja a criação de testes baseados numa ==análise do código== para testar se o fluxo do programa é seguido de acordo com o previsto, sua grande vantagem é ser simples de implementar já que entender o seu código é um caminho muito mais bem definido do que pensar apenas em especificações. Um glass-box testing é dito ***path-complete*** se for capaz de testar todos os caminhos possíveis no seu programa, o que geralmente é impossível, porém há dicas que podem nos ajudar a alcançar uma maior cobertura de testes:
- Teste todos as bifurcações das suas definições `if-elif-else`
- Teste todas as cláusulas de `except`
- Para cada looping teste os casos onde o programa não entra no loop, entra e executa apenas uma vez e que ele entra e executa mais de uma vez.
- Para loopings baseados em expressões booleanas complexas, teste cada possibilidade de valoração para a expressão
- Para [[Funções]] recursivas teste quando apenas o caso base é executado (Não há chamadas recursiva), quando há apenas uma chamada recursiva e quando há mais de uma chamada recursiva

# Conduzindo os testes 
Para gerar a maior cobertura possível , os testes podem ser separados em 3 classes que maximizam a eficiência dos testes: **Testes Unitários, Testes de Integração e Testes Funcionais**:

## Testes unitários
Os testes unitários baseiam-se em testar eficientemente cada *unidade* do seu código, ou seja, cada função e classe do seu programa.

## Testes de integração
Os testes de integração, por sua vez, baseiam-se na premissa de testar o funcionamento conjunto das unidades do seu código, como uma função lida com a outra, seus métodos de classe estão bem definidos e etc.

## Testes funcionais
O testes funcionais são os maiores e mais complexos, seu objetivo é atestar que o seu programa como um todo funciona da maneira que deveria.

# Drivers e Stubs
Durante o desenvolvimento, será necessários várias vezes testar partes do nosso código que possuem dependências ou que são apenas dependências, dentro da estrutura completa do programa , de partes que nem sequer foram criadas, para possibilitar os testes nessa fase de desenvolvimento nós usamos os ***Drivers e Stubs*** para simular essas partes ainda não construídas do software, outro caso em que essas ferramentas são amplamente utilizadas é para simular a comunicação com o banco de dados quando não for possível 

### Drivers
Os drivers tem o objetivo de representar partes dó código que possuem a função como dependência, simular a real e futura aplicação da unidade que está sendo testada.

### Stubs
Os stubs, por sua vez pretendem substituir partes do código que são dependências da unidade testada que ainda não existem, retornando valores fixos que condizem com o possível funcionamento da parte real quando for implementada.

# Testes regressivos
O ideia é que os testes sejam sempre *regressivos*, ou seja, que o programa viva num ciclo infinito de teste-alteração e que após cada mínima alteração o programa passe por todos os testes para que seja possível garantir que uma correção ou implementação não gerou outros erros.