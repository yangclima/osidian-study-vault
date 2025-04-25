No dia 6, continuamos abordando o [[Dia 5#Versionando com Git|versionamento com git]], chegou a hora de sincronizar a sua linha do tempo local, com a linha do tempo do seu repositório remoto .
# Sincronizando os repositórios
Agora é a hora de sincronizar os repositórios, unir a linha do tempo que você criou no seu computador com a linha do tempo do seu repositório remoto, **empurrar** as mudanças locais para a nuvem, isso é feito através do comando `git push`:
```bash
git push
```
Ao executar esse comando, todos os seus commits serão enviados para o repositório remoto e passarão a integrar a linha do tempo dele, sincronizando assim as linhas do tempo, assim, esse processo se torna cíclico, você modifica ou adiciona arquivos para realizar melhorias ou alterações no seu projeto, enquadra esse arquivos na foto com `git add` e depois tira a foto adicionando-a na sua linha do tempo com `git commit`, depois de alguns commits você sincroniza os repositórios e então volta ao início do ciclo.
# Conflitos na sincronização
Se você cometer algum erro e tentar usar `git commit --amend` num commit que já está no repositório remoto e posteriormente tentar executar um `push`, o git te impedirá de fazê-lo, e está cumprindo o seu papel, já que algo com certeza está errado, as linhas do tempo já não fazem sentido juntas então um conflito está ocorrendo, há uma forma de burlar isso, usando o seguinte comando:
```bash
git push --force
```
Ou
```bash
git push -f
```
Porém, esse é um comando perigoso, o que está acontecendo é que você está basicamente forçando a barra, chutando a porta, ordenando que o git confie na sua linha temporal independente da linha temporal do repositório remoto e substituindo o que for preciso para que o push seja feito, o que pode interferir no trabalho das outras pessoas que estão trabalhando no repositório. 
# Não tenha medo dos logs de erro
> É melhor uma mensagem de erro que um erro invisível.

# Build
> Build é o processo de transformar e optimizar os arquivos locais montando-os num configuração que poderá ficar eficientemente disponível na internet. 