No dia 19, aborda-se algumas facilidades para utilizar-se no ambiente de desenvolvimento, em especial o VS code. 
# Utilizando Absolute Path no node
Para evitar o uso de caminhos relativos, podemos utilizar um arquivo especial de configuração do Vs code, o `jsconfig.json`, utilizando o format a seguir:
```json
{
  "compillerOptions": {
    "baseUrl": "."
  }
}
```
A partir de agora, você pode utilizar caminhos de imports no formato `infra/database.js` ao invés de `../../../../infra/database.js`, ou seja, utilizar caminhos absolutos baseados na raiz do projeto.
# Uma dica sobre testes
As vezes, testamos só o estado de acerto, porem, é essencial, para garantir que o teste é bem formulado que nos atentemos a verificar também que o teste acusa um erro no caso de um mau comportamento do nosso programa. 
# Configurando scripts dos serviços
Podemos adicionar o seguinte nos scripts no `package.json` do [[Dia 3#Node Package Manager (npm)|npm]] para facilitar o fluxo de trabalho:
```json
"services:up": "docker compose -f infra/compose.yaml up -d",
"services:stop": "docker compose -f infra/compose.yaml stop",
"services:down": "docker compose -f infra/compose.yaml down",
```
# Fuzzy search
A fuzzy search é um feature do vscode que permite acessar arquivos do projeto mais facilmente, sem precisar acessar a árvore de arquivos, o comando para acessar a fuzzy search é `Ctrl + P`e além disso, ela permite usar o modificador `@` para cessar diretamente partes de um arquivo, por exemplo `package@scripts` the leva direto para os scripts do `package.json`.

