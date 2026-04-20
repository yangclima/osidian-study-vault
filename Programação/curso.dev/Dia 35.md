O Dia 35 foi o dia de terminar as refatorações gerais do projeto, iniciadas no [[Dia 34]], tomando os devidos cuidados para não ser atingido pelo **Efeito Estilingue Infinito**. Imagine que fazer o lançamento de um projeto ou aplicação é como atirar uma pedra com o estilingue, por vezes, sobretudo em projetos pessoais, onde não há cobrança externa, puxamos a pedra por tempo demais, tanto pelo medo de errar o alvo quanto por querer que esse lançamento seja extremamente preciso, porém, quanto mais puxamos a pedra, mais longe ela fica o alvo, a perfeição é um estado inatingível, portanto, por vezes, vale mais apena adotar aquele nosso crescimento orgânico, isto é, lançar e adaptar conforme o necessário, que ficar lapidando tanto que no final, nunca chegamos a lugar nenhum.

O primeiro passo das refatorações é melhorar a forma como os  scripts da nossa aplicação estão organizados e sua execução. Queremos que após os scripts `test` e  `dev` do `npm`, os servidores locais da database, que rodam num container docker sejam finalizados, para isso criaremos o  script `posttest`: 

```json
"posttest": "npm run services:down"
```

Sempre que criamos um script `post + <script name>` o `npm` entende que deve executar aquele script após uma execução com sucesso do script `<script name>`, nesse caso, porém, note que se os testes falharem, os  serviços não serão derrubados, o que pode ser útil, para que possamos checar o estado de falha do database.

O próximo passo é então refatorar os testes em si, melhorando a qualidade das sua descrições. Para isso, as duas principais metodologias são o TDD, *Test Driven Development* e o BDD, *Behavior Driven Development*, na primeira, os únicos envolvidos são o programadores, o que acende o risco de que os testes sejam puramente técnicos e não reflitam exatamente o que de fato precisa ser testado: O funcionamento da aplicação para as necessidades do usuário final. Na segunda metodologia, geralmente estão envolvidos no processo, além dos programadores, pessoas de *Business* e de *Quality Assurance* e a ideia é que os testes sejam voltados ao funcionamento e *comportamento* real da aplicação.


Dentro do BDD, um padrão muito adotado hoje em dia é o `Gherkin`, "Pepino em conserva" na tradução literal, o que faz referência ao ato de dividir os testes em partes fáceis de consumir, seja por pessoas de negócios ou pessoas de tecnologia, e que são preservados independentemente da implementação, nessa metodologia os testes são descritos pela seguinte estrutura:

```
GIVEN X

WHEN Y

THEN Z
```

Por exemplo:

```
GIVEN that the user is not logged in

WHEN the user make a POST request to api/v1/migrations

THEN the migrations shold be executed sucessfully 
```

Essa abordagem é muito completa e resolve um problema muito comum: Muitas vezes as descrições dos testes descasam com sua implementação, por exemplo, podemos inicialmente exigir que um endpoint retorne `200` e frisar isso tanto na descrição do teste com um `Should return 200` quanto com um `expect(response.status).toBe(200)` e então mudar o esperado para um `201` e esquecer de mudar na descrição, nesse caso, quem está certo? A descrição ou a implementação? Para evitar esse conflito, limitamos questões de comportamento às descrições dos testes e a implementação para o código em si de cada teste.

Uma alternativa mais simples, e que foi adotada nos testes do Tabnews é dividir cada teste em **Contexto** e **Afirmação**, o primeiro expresso nas descrições, por exemplo ``POST api/v1/migrations`` > `Anonymous User` > `Running Pending Migrations` e o segundo, a **Afirmação**, tendo como única fonte de verdade a implementação, isto é, o código real de cada teste, por exemplo:

```js
describe('POST /api/v1/migrations', () => {
  describe('Anonymous user', () => {
    describe('Running pending migrations', () => {
      test('For the first time', async () => {
        const response1 = await fetch(
          'http://localhost:3000/api/v1/migrations',
          {
            method: 'POST',
          }
        );
        
        const response1Body = await response1.json();
        
        expect(response1.status).toBe(201);
        
        expect(Array.isArray(response1Body)).toBe(true);

        expect(response1Body.length).toBeGreaterThan(0);
      });
  
      test('For the second time', async () => {
        const response2 = await fetch(
          'http://localhost:3000/api/v1/migrations',
          {
            method: 'POST',
          }
        );

        const response2Body = await response2.json();

        expect(response2.status).toBe(200);

        expect(response2Body.length).toEqual(0);
      });
    });
  });
});
```

Nesse formato, não corremos o risco de ter uma descrição desatualizada com relação aos testes ou vice-versa
