No dia 15, o tema chave é "testes automatizados", por que ele são tão importantes? Vamos aprender a executá-los de maneira profissional adicionando mais uma dependência ao nosso [[Dia 2#Ambiente de Desenvolvimento|Ambiente de desenvolvimento]].

# Testes Automatizados
Uma das grandes preocupações, sobretudo depois que você já tiver uma versão funcional da sua aplicação é garantir que ela tenha um crescimento saudável, que possamos adicionar novas features sem sofrer **regressão**, ou seja, sem quebrar nada que já está pronto, para isso aplicamos o [[Teste de Software]] e para automatizar esse processo e ter uma maior facilidade no desenvolvimento, utilizamos ferramentas que permitem acompanhar a evolução do nosso código cada modificação, garantindo que tudo está em seu lugar. 

Para isso, usamos um framework de teste. No caso do JavaScript existem vários frameworks, e cada um tem como proposta lidar com os testes de uma forma diferente, porém, o framework que de longe é mais utilizado é o *Jest*.
# Instalando o *Jest*
Para instalar o Jest, como sempre, utilizaremos o [[Dia 3#Node Package Manager (npm)|npm]] através do comando
```bash
npm install --save-dev jest
```
Além disso, definimos no `package,json` os nossos scripts de teste:
```json
"test": "jest",
"test:watch" "jest --watch"
```
O primeiro comando executa os testes uma única vez, já o segundo ativa uma opção que passa a conferir as alterações do código executando os testes sempre que detectar uma mudança.

Por padrão, o Jest, procura no seu repositório por arquivos que possuem o seu nome terminado com `.test`, por exemplo `Home.test.js` e a estrutura básica de um teste é:

```javascript
test("Nome do teste", () => {
  expect(1).toBe(1)
})
```

Cada arquivo que segue esse padrão é uma suite de teste, e pode conter vários testes como esse acima, o padrão é bem intuitivo, a estrutura base dos teste é pegar um valor que o nosso código retorna e comparar com o que ele deveria retornar, se esses valores forem iguais, o teste passa.
# Test Driven Development (TDD)
O processo mais natural é construir algo e depois testá-lo, é lógico, porém, fazer o inverso pode ser de grande ajuda, se já soubermos o que nossa implementação precisa fazer, podemos criar os testes com base no objetivo que pretendemos alcançar (O que nosso código deve fazer) e ir utilizando o retorno desses testes para nos aproximar cada vez mais do objetivo, é como se os testes fossem nos dizendo se estamos quente ou frio.

Um ponto importante a se levar em consideração é, tenha muita atenção ao criar seus testes, afinal, eles não garantem que sua aplicação funciona, apenas, que ela faz o que VOCÊ espera que ela faça, ou seja, criar os testes errados fará você ter uma noção errada sobre o funcionamento ou não da aplicação.

# Transpiling
O suporte do Jest para módulos ECMAScript (ESM) é experimental, ele lida melhor com imports do tipo CommonJs, para resolver essa divergência e continuar usando ESM sem afetar o funcionamento do Jest, fazemos o transpiling do código.
