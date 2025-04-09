Ao criar scripts que realizam tarefas complexas não é nada viável que sempre que quisermos, por exemplo, calcular a raiz quadrada de um número nós precisemos sempre reescrever todo o algoritmo que estiver utilizando em cada parte do nosso código em que esse cálculo for necessário, além de ser difícil criar o código, ficará também cada vez mais complicado mantê-lo, afinal, quanto mais linhas de código maior a chance de cometer um erro, além disso, quando precisarmos alterar algo simples no nosso código, teremos que fazer alterações em muitas linhas do nosso código, esse problema é resolvido pelas **funções**, ferramentas utilizadas para tornar pedaços do nosso código reutilizáveis.

O principal objetivo das funções é prover **abstração**, ou seja, ocultar detalhes desnecessários do código e prover **decomposição**, ou seja, nos permitir quebrar os nosso problemas em pedaços menores. 

# Escopo
A maioria das linguagens tem o que chamamos de escopo de função, isso quer dizer que, ao definirmos uma função, é criado um novo *naming space* para as variáveis, isso quer dizer que as variáveis de dentro da função não são as mesmas de fora dela e as variáveis criadas dentro de uma função só existem enquanto a execução dela está ocorrendo. Lembre-se sempre que uma função herda o escopo em que foi criada, se uma variável é acessível no escopo em que uma função é criada, ela será acessível no escopo dela.

# Funções em cada linguagem
## Python
```python
def nome_da_funcao(parametro1: type, parametro2 = "ValorPadrão") -> string:
    """
    Specifications
    """

	# Bloco de código
	print("Hello world")

	# retorno
	return "This is my function's return"

# Chamando a nossa função
nome_da_funcao("argumento posicional", parametro2 = "argumento de palavra-chave")
```
Perceba que em python (Pelo menos nas versões recentes) nós podemos definir as especificações na própria assinatura da função, também na assinatura podemos definir valores-padrão para nossos parâmetros.