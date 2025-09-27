Enquanto o [[Prettier]] ajuda a definir padrões estilísticos, o `Eslint` ajuda a evitar falhas como variáveis criadas mas nunca usadas ou a utilização de variáveis não declaradas, em geral, algumas más práticas de desenvolvimento. 

O [[Next]] cria automaticamente um arquivo `eslint.config.mjs` quando selecionamos o `Eslint` como linter durante a execução do comando `create-next-app`, na seguinte forma:

```js
import { dirname } from 'path';
import { fileURLToPath } from 'url';
import { FlatCompat } from '@eslint/eslintrc';

const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

const compat = new FlatCompat({
  baseDirectory: __dirname,
});

  
const eslintConfig = [
  ...compat.extends('next/core-web-vitals'),
  {
    ignores: [
      'node_modules/**',
      '.next/**',
      'out/**',
      'build/**',
      'next-env.d.ts',
    ],
  },
];

export default eslintConfig;
```

Não se assuste se você está acostumado com a antiga sintaxe do `Eslint` nos arquivos `.eslintrc.json`, basicamente o `FlatCompat` é um utilitário do `Eslint` para prover compatibilidade com aquele antigo formato que usava a tag `extends`, ou seja, a parte importante do código acima é, de forma superficial, a linha

```js
...compat.extends('next/core-web-vitals'),
```

Que substitui o antigo `extends: ['next/core-web-vitals']`. 

Em geral, na forma atual, o arquivo, gerado pelo `Next` só adiciona algumas regras básicas de utilização, sobretudo, do react, podemos então adicionar as regras recomendadas do `Eslint` para JavaScript, o que pode ser feito importando o seguinte:

```js
import js from '@eslint/js';
```

E dentro do nosso objeto `eslintConfig` adicionamos:

```js
js.configs.recommended
```

Se você também estiver utilizando o `Prettier`, pode haver algumas incompatibilidades, conflitos entre as regras do `Eslint` e do `Prettier`, para evitar isso, utilizamos o pacote `eslint-config-prettier` instalado através do `npm`:

```bash
npm i eslint-config-prettier
```

E o adicionamos no nosso arquivo `eslint.config.mjs` importando o seguinte:

```js
import eslintConfigPrettier from 'eslint-config-prettier/flat';
```

Note que o pacote já provê uma versão adaptada para as novas versões do `Eslint` (Perceba o `/flat` no final do import), assim, basta adicionarmos o item importado dentro do objeto `eslintConfig`

```js
eslintConfigPrettier
```

Por fim, outro problema que pode aparecer é a incompatibilidade com o [[Jest]] que pode ser resolvido com o pacote `eslint-plugin-jest`:

```bash
npm i eslint-plugin-jest
```

Que é importado da seguinte forma:

```js
import pluginJest from 'eslint-plugin-jest';
```

E pode ser configurado adicionando o seguinte ao nosso arquivo objeto `eslintConfig`:

```js
{
  files: ['**/*.spec.js', '**/*.test.js'],
  plugins: { jest: pluginJest },
  languageOptions: {
    globals: pluginJest.environments.globals.globals
  }
}
```

Juntando a 3 adaptações nosso `eslint.config.mjs` fica:

```js
import { dirname } from 'path';
import { fileURLToPath } from 'url';
import { FlatCompat } from '@eslint/eslintrc';

// Imports adicionados
import js from '@eslint/js';
import pluginJest from 'eslint-plugin-jest';
import eslintConfigPrettier from 'eslint-config-prettier/flat';

const __filename = fileURLToPath(import.meta.url);
const __dirname = dirname(__filename);

const compat = new FlatCompat({
  baseDirectory: __dirname,
});
  
const eslintConfig = [
  ...compat.extends('next/core-web-vitals'),
  // Objetos adicionados
  eslintConfigPrettier,
  js.configs.recommended,
  {
    files: ['**/*.spec.js', '**/*.test.js'],
    plugins: { jest: pluginJest },
    languageOptions: {
      globals: pluginJest.environments.globals.globals,
    },
  },
  {
    ignores: [
      'node_modules/**',
      '.next/**',
      'out/**',
      'build/**',
      'next-env.d.ts',
    ],
  },
];

export default eslintConfig;
```