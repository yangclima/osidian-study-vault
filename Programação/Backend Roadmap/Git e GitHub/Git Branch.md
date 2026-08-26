O comando git branch é usado, em geral, para manipular as [[Manipulação de branches|branches]], listá-las, criá-las ou deletá-las.

```bash
git branch [--color[=<when>] | --no-color] [--show-current]
	   [-v [--abbrev=<n> | --no-abbrev]]
	   [--column[=<options>] | --no-column] [--sort=<key>]
	   [--merged [<commit>]] [--no-merged [<commit>]]
	   [--contains [<commit>]] [--no-contains [<commit>]]
	   [--points-at <object>] [--format=<format>]
	   [(-r|--remotes) | (-a|--all)]
	   [--list] [<pattern>…​]
git branch [--track[=(direct|inherit)] | --no-track] [-f]
	   [--recurse-submodules] <branch-name> [<start-point>]
git branch (--set-upstream-to=<upstream>|-u <upstream>) [<branch-name>]
git branch --unset-upstream [<branch-name>]
git branch (-m|-M) [<old-branch>] <new-branch>
git branch (-c|-C) [<old-branch>] <new-branch>
git branch (-d|-D) [-r] <branch-name>…​
git branch --edit-description [<branch-name>]
```

Para listar as branches, usamos

```bash
git branch --list

# Ou simplesmente
git branch
```

Podemos ainda listar apenas as branches que obedecem um determinado pattern, por exemplo, para incluir apenas feature branches, podemos usar

```bash
git branch --list 'feature/*'
```

Por outro lado, para listar as branches que possuem um determinado commit, usamos o hash do commit seguindo:

```bash
git branch --contains <hash do commit>
```

Outras opções são `--no-contains`, `--merged` e `--no-merged`, onde merged se refere a branches que já foram mergeadas, isto é, cujo histórico de commits já está totalmente contido para trás do commit dado como argumento.

