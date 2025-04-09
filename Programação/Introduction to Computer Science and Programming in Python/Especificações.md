O termo ==*specifications*==  ou especificações se  refere ao conjunto de definições que funcionam como uma espécie de contrato entre o criador de um código e os clientes (As pessoas que pretendem utilizar aquele código),. As *specifications* podem ser divididas em duas partes: *Assumptions* e *Guarantees* - Suposições e Garantias - as **suposições** listam regras que devem ser seguidas pelos clientes para o bom funcionamento de um determinado pedaço de código, normalmente uma [[POO e Classes|classe]] ou uma [[Funções|função]],  já as **garantias** são definições que serão seguidas pelo código, desde que as suposições tenha sido atendidas. Em python, por definição, utilizamos as chamadas *Docstrings*,  definidas entre aspas duplas triplas para criar as nossas especificações .
```python
def square_root(x, epsilon):
	# Specifications:
	"""
	# Assumptions:
	Assumes x and epsilon a int or float
	    epsilon > 0 & x > 0

	# Guarantees:
	Return float y such that y**2 is within epsilon of x
	"""
	guess = x/2

	while(abs(guess**2 - x) >= epsilon):
	    guess = guess - (((guess**2) - x)/2)

	return guess
```