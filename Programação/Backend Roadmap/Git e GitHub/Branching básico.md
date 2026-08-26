O chamado Branching é um dos principais recursos do Git, essencial para facilitar o trabalho e repositórios e uma dos seus principais fluxos de utilização pode ser exemplificado no seguinte exemplo:

Digamos que você está trabalhando no desenvolvimento de um site, para criar uma nova feature, digamos, um sistema de comentários, você cria uma nova branch `feature/comments` do seu repositório a partir da branch de produção e começa a trabalhar, no meio do desenvolvimento, você é interrompido com uma nova issue emergencial, digamos, uma falha de segurança, então você volta para a branch de produção, cria uma nova branch `hotfix/security`, resolve a falha, faz o merge com a branch de produção e empurra as modificações para o repositório remoto, em seguida, retorna para a branch `feature/comments` e continua sua implementação.

Esse é um fluxo que seria impossível de fazer sem utilizar as branches e que torna o nosso fluxo de desenvolvimento muito mais prático.

Vejamos agora na prática: Digamos agora que estamos numa branch `master` (Nossa branch de produção) com um conjunto de commits já aplicados nela:

![[ber_006.png]]

Para começar o desenvolvimento de uma nova feature, queremos então criar a branch `feature/comments`, para isso, usamos:

```bash
git branch 'feature/comments'
```

Então, mudamos para a nova branch usando:

```bash
git checkout 'feature/commments'
```

Podemos ainda fazer esses dois comandos em um só, usando:

```bash
git checkout -b 'feature/comments'
```

Obtendo como resultado:

![[ber_005.png]]

A partir daí, podemos livremente criar novos commits nessa branch, por exemplo:

```bash
git commit -m 'feat: add `create-comments-table` migration'
```

Obtendo:

![[ber_007.png]]

Agora, quando recebemos a issue de uma falha crítica, graças ao `Git`, não precisamos fazer o deploy das modificações de `feature/comments` junto com as modificações que resolvem a issue, nem nos dar o trabalho de reverter essas modificações, basta voltar a branch master e de lá criar uma outra branch.

Note, entretanto, que se tivermos modificações em staging não será possível trocar de branch, precisamos manter nosso work state limpo. Considerando que não temos nada em staging, voltamos a branch `master` usando:

```bash
git checkout master
```

Daí, com o sistema que, agora retornou ao ponto onde estávamos exatamente antes de criar `feature/comments`, criamos a branch `hotfix/security` usando:

```bash
git checkout -b 'hotfix/security'
```

Fazemos as alterações e então seu commit usando:

```bash
git commit -m 'fix: security issue'
```

Obtendo:

![[ber_008.png]]

A partir daí, fazemos nossos testes, garantimos o funcionamento das modificações e então, estamos aptos a fazer o merge de `hotfix/security`, para isso, primeiro voltamos para a branch sobre a qual a mesclagem será realizada (Nesse caso, a `master`) e então executamos:

```bash
git merge 'hotfix/security'
```

Nesse caso, como o commit `C4` para o qual `hotfix/security` aponta está diretamente a frente do commit `C2` para o qual a `master` aponta, o último comando deve exibir entre suas saídas `fast-foward`, de forma simplificada, como o commit que está sendo mesclado sobre a `master` pode ser alcançado simplesmente seguindo o histórico de commits, sem conflito, o `Git` simplesmente avança o ponteiro da branch `master` para o commit `C4`, obtendo:

![[ber_009.png]]

Tendo então finalizado a utilização de `hotfix/security` podemos deletá-la usando o comando:

```bash
git branch -d 'hotfix/security'
```

Voltamos então a trabalhar na branch `feature/comments` fazendo um novo commit e obtendo a seguinte situação:

![[ber_010.png]]

Agora, após finalizar as alterações de `feature/comments` voltamos à branch `master` para incorporar as alterações e executamos:

```bash
git merge 'feature/comments'
```

Agora, o resultado será um pouco diferente, como a linearidade dos commits já não existe aqui, a saída deve mostrar algo como `recursive`, basicamente o git criará um novo commit que aponta simultaneamente para `C4` e `C5` e moverá o ponteiro da `master` para ele, obtendo:

![[ber_011.png]]

Esse processo, no entanto, pode não ocorrer suavemente, isso, quando surgirem conflitos entre as duas branches, nesse caso, o `Git` não será capaz de criar sozinho o commit de merge, ele pausa o processo até que os conflitos sejam resolvidos, nesse ponto, para ver que arquivos apresentam conflitos usamos:

```bash
git status
```

Todos os arquivos com conflitos estarão listados como ``unmerged`` e apresentarão marcadores como, por exemplo:

```html
<<<<<<< HEAD:index.html
<div id="footer">contact : email.support@github.com</div>
=======
<div id="footer">
 please contact us at support@github.com
</div>
>>>>>>> feature/comments:index.html
```

Nesse bloco, tudo acima de ` ======= ` pertence a `HEAD`, a branch na qual você estava quando executou o ``git merge`` enquanto tudo abaixo dele pertence a branch `feature/comments` , que está sendo aplicada sobre ela, você pode então resolver esse conflito, substituindo esse bloco inteiro por, digamos, `<div id="footer">contact : email.support@github.com</div>` (Selecionando a versão do `HEAD`) e então executar um `git add` para marcar o conflito como resolvido.

Para resolver todos os conflitos de merge você deve checar conflito a conflito e resolver todos, uma forma mais fácil e visual de fazer isso é usando o comando:

```bash
git mergetool
```

Depois de resolver tudo, podemos verificar o status usando `git status` e devemos receber entre os retornos do comando, a mensagem:

```
All conflicts fixed but you are still merging.
```

Para concluir, usamos:

```bash
git commit 
```

Será então aberto o arquivo do commit com uma mensagem padrão, que você pode fechar para continuar ou alterar como quiser.