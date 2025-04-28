O dia 24 foi voltado a resolução de algumas incompatibilidades do [[Dia 15#Instalando o *Jest*|Jest]], no caso, os [[Dia 19#Utilizando Absolute Path no node|absolute paths]] e os imports no formato *ESModules*, através do [[Dia 15#Transpiling|Transpiling]] simplificado através do [[Dia 3#Next.js|Next.js]].
# Testes do banco de dados
## Rodando testes linearmente
Por padrão, o Jest executa os testes de forma concorrente, ou seja, simultaneamente, porém, para permitir os testes do banco de dados, precisamos limpá-lo antes de cada suite de teste, para isso, os testes precisam ser executados de forma linear, para isso, utilizamos no comando de testes a flag `--runInBand`, no `package.json` os testes então ficam definidos como:
```json
{
  "test": "jest --runInBand",
  "test:watch" "jest --watchAll --runInBand"
} 
```
## Limpando o banco de dados
Para que os testes do banco de dados funcionem corretamente precisamos limpar o schema do nosso banco de dados entre cada teste, para que uma query não influencie na outra, para isso (Limpar o DB), podemos utilizar a seguinte query: 
```SQL
DROP schema public cascade; CREATE schema public;
```
E para de fato executar essa query entre cada teste, no arquivo de testes, utilizamos o seguinte: 
```javascript
beforeAll(( ) => {
  await database.query("DROP schema public cascade; CREATE schema public;")
});
```
OBS: É essencial utilizar o `await` para evitar erros.
# Transpiling no jest
Para configurar o transpiling do jest, para resolver ops problema citado, basta configurá-lo através do arquivo `jest.config.js`, utilizando o módulo fornecido pelo Next.js:
```javascript
// jest.config.js

const nextJest = require("next/jest");

const createJestConfig = nextJest({dir: "."});
const jestConfig = createJestConfig({
  moduleDirectories: ["node_modules", "<rootDir>"]
})

module.exports = jestConfig
```
Um outro problema que pode e irá surgir é que o Jest não receberá as variáveis de desenvolvimento do `NODE_ENV=development` já que executa com`NODE_ENV=test`, assim, para que as varáveis de ambiente de desenvolvimento sejam passadas para o jest precisamos definir todas as variáveis num arquivo `.env` ao invés de `.env.development` ou, configurar o módulo `dotenv` no jest adicionando o seguinte no arquivo `jest.config.js`:
```javascript
// jest.config.js

const dotenv = require("dotenv");
dotenv.config({
  path: ".env.do=evelopment"
});
```
# Divide and Conquer
Mais um vez, é importante frisar o quão esse de desenvolver os projetos de maneira [[Dia 8#Programação Orgânica Vs. Impressora 3D|orgânica]] dividindo em pequenos passos e executando, evoluindo aos poucos, ou seja, dividindo e conquistando e ainda mais importante é não perder o objetivo de negócios de vista, lembrando sempre que o modelo e a execução técnica não passam de uma maneira de alcançar esse objetivo, e que não faz sentido desenvolver algo que não resolva nada e não seja útil de nenhuma forma.
