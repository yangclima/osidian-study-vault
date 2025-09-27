# Instalação
```bash
npm install prisma -D
npm install @prisma/client
```
# Inicialização
```bash
npx prisma init
```
Após esse comando o `prisma` criará uma pasta chamada 'prisma' com um arquivo `schema.prisma` onde você criará os modelos do seu banco de dados, além disso, nesse arquivo, haverá o seguinte:

```prisma
datasource db {
  provider = "postgresql"
  url      = env("DATABASE_URL")
}
```

Isso aponta o local do arquivo `.env` onde deve existir a variável de ambiente `DATABASE_URL` que servirá para que o prisma se conecte na sua base de dados.

O próximo passo é criar no arquivo `schema.prisma` os modelos que irão estabelecer as tabelas do seu bando de dados, por exemplo:

```prisma
model Task {
  id            Int      @id @default(autoincrement())
  title         String   @db.VarChar(255)
  createdAt     DateTime @default(now()) @db.Timestamp(6)
  content       String?
  isDone        Boolean  @default(false)
  totalTime     Int
  remainingTime Int
}
```

Agora, já podemos criar as tabelas no banco de dados usando o comando:

```bash
npx prisma migrate dev --name nome-da-migration
```

Uma vez que você já criou uma migração, se for necessário rodar essa migração novamente, se não houver alteração no `schema.prisma` o ideal é utilizar o comando:

```bash
npx prisma migrate dev
```

Depois disso, quando for construir a interface de conexão com o banco de dados você precisa **gerar o cliente prisma**, o que pode ser feito através do comando a seguir:

```bash
npx prisma generate
```

Naquele arquivo `schema.prisma` gerado pelo `npx prisma init` haverá também as especificações a seguir, geradas automaticamente:

```prisma
generator client {
  provider = "prisma-client-js"
  output   = "../generated/prisma"
}
```

A especificação `output` determina onde o seu cliente será gerado, é de lá que você importará o `PrismaClient` para manipular o banco de dados, nesse caso, o nosso `import` fica:

```js
import { PrismaClient } from "../generated/prisma/index.js";
```

Isso para um arquivo que fica dentro da pasta `/infra`.

# Utilizando o `PrismaClient`
Antes de tudo, precisamos instanciar o nosso cliente Prisma:

```js
const prisma = new PrismaClient();
```

Agora, utilizamos esse objeto para lidar com o nosso banco de dados. Para criar uma instância do objeto `Task` que criamos no nosso `schema.prisma`, utilizamos o seguinte:

```js
const newTask = prisma.task.create({
  title: "Praticar Prisma",
  content: "Criar migrations e seed",
  totalTime: 600,
  remainingTime: 600,
  isDone: false,
})
```

Para criar vários ao mesmo tempo podemos usar o seguinte:

```js
const newTasks = prisma.task.createMany({
  data: [
  {
	title: "Estudar React",
	content: "Focar em hooks e context API",
	totalTime: 600,
	iningTime: 600,
	isDone: false,
  },
  {
	title: "Praticar Prisma",
	content: "Criar migrations e seed",
	totalTime: 1200,
	remainingTime: 800,
	isDone: false,
  },
  {
	title: "Revisar Cálculo",
	content: "Exercícios da lista 2",
	totalTime: 900,
	remainingTime: 0,
	isDone: true,
  },
],
});
```

É importante lembrar que as funções de interação com o banco de dados são assíncronas o que pode gerar problemas se não estiverem acompanhadas do `await`.

Para deletar uma instância que está no nosso banco de dados, utilizamos:

```js
const deletedTask = await prisma.task.delete({
  where: {id: 3}
})
```

Para atualizar uma instância usamos:

```js
const updatedTask = await prisma.task.update({
  where: {id: 3},
  data: {
    remainingTime: 340,
    isDone: true,
   }
})
```