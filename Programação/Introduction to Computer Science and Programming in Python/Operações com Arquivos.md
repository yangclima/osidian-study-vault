O Python possui features muito bem desenvolvidas para o manuseio de arquivos, baseando-se principalmente no *file handler*, através do qual conseguimos abrir e manusear arquivos independente do sistema operacional através da função *built-in* `open()`:
```python
# As barras inversar duplas são devido ao sistema de arquivos windows
FILE_PATH = 'C:\\users\\YAN\\kids.txt'

# O primeiro argumento é a localização do arquivo, o segundo é 'w', 'r' ou 'a'
# 'w' de write serve para escrever o arquivo do 0, ou reescrevê-lo
# 'r' de read serve para acessar o conteúdo de um arquivo já existente
# 'a' de append serve para adicionar informações ao arquivo já existente
fh = open(FILE_PATH, 'w')

for i in range(2):
    name = input("Enter name ")
    # A função write, oriunda do objeto retornado pelo fileHandler
    fh.write(name + '\n') # \n é um caractere especial usado para inserir uma linha

# Para evitar erros é imprescindível fechar o arquivo no final
fh.close()
```
As principais funções de manuseio de arquivos no python são:

| Função             | Utilização                                                                           |
| ------------------ | ------------------------------------------------------------------------------------ |
| `open(fn, 'w')`    | Cria um arquivo para escrever e retorna o *file handler*                             |
| `open(fn, 'r')`    | Abre um arquivo existente para ler e retorna o *file handler*                        |
| `open(fn, 'a')`    | Abre um arquivo existente para adicionar informações e retorna o *file handler*      |
| `fh.read()`        | Retorna uma string com o conteúdo do arquivo                                         |
| `fh.readlines()`   | Retorna uma lista onde cada item é uma string com o conteúdo de uma linha do arquivo |
| `fh.write(s)`      | Escreve a string `s` no final do arquivo                                             |
| `fh.writelines(S)` | Escreve cada item de `S` - uma sequência de strings - no arquivo                     |
| `fh.close()`       | Fecha o arquivo                                                                      |
