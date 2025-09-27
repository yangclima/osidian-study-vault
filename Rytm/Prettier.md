Já sabemos que é essencial manter um padrão na escrita do código para evitar diversos possíveis problemas que venham a ocorrer devido a incongruências na maneira em que o código é escrito, para isso, existem diversas ferramentas úteis, uma delas é o `Prettier`, um formatador de código opinativo que formata o seu código na hora do salvamento do arquivo e segue definições muito amplas decididas por você.

Para instalar o `Prettier` usamos:

```bash
npm i -D prettier
```

Podemos então criar um arquivo `.prettierrc` com as configurações que queremos usar no projeto:

```json
// .prettierrc
{
  "singleQuote": true,
  "trailingComma": "all",
  "printWidth": 80
}
```

Além disso, é útil criar um arquivo `.prettierignore` para adicionar pastas e arquivos que não deve ser analisados pelo `Prettier`, como pastas de build a exemplo da pasta `.next`:

```
.next/
```

A utilização do `Prettier` pode ser feita através de dois comandos básicos que podem ser adicionados aos scripts do nosso `package.json`:

```json
{
  "lint:check": "prettier --check .",
  "lint:fix": "prettier --write .",
}
```