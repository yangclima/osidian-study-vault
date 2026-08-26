# Criar uma branch
Para criar uma branch usamos o comando

```bash
git branch <nome da nova branch>
```

Para criar e, ao mesmo tempo mudar para a nova branch, usamos:

```bash
git checkout <nome da nova branch>
```
# Trocando de branch
Para mudar para uma outra branch, usamos o comando:

```bash
git checkout <nome da branch>
```

# Renomeando uma branch
Para mudar o nome de uma branch, usamos o comando:

```bash
git branch -m <nome antigo> <novo nome>
```

Ou, se estivermos mudando o nome da branch atual, simplesmente:

```bash
git branch -m <novo nome>
```

# Deletando uma branch
Para deletar um branch, usamos o comando:

```bash
git branch -d <nome da branch>
```

Esse comando, entretanto, não funcionará a menos que a branch esteja atualizada com a branch remota (Tivermos realizado o ``push`` e o `merge` dessa branch), para deletar mesmo que ela não esteja atualizada, usamos:

```bash
git branch -d --force <nome da branch>
```

Ou o atalho:

```bash
git branch -D <nome da branch>
```