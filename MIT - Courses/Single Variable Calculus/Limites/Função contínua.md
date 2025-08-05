---
tags:
  - Definição
---
Intuitivamente podemos definir uma função contínua como aquela que pode ser esboçada sem que seja necessário tirar o lápis do papel, porém essa definição é rasa, pois bem, podemos definir a continuidade de uma função da seguinte forma:
$$
f(x) \ \text{é contínua em } p \iff

\begin{cases}

	\forall \epsilon > 0, \exists \delta > 0 \ \text{tal que} \ \forall x \in D_f; \\
	|x - p| < \delta \implies |f(x) - f(p)| < \epsilon 

\end{cases}
$$
Note a semelhança entre essa definição e a definição de [[Limite]], não é a toa, é devido a isso que podemos definir continuidade da seguinte forma:
$$
f \text{ é contínua em } x = p \iff \lim\limits_{x \rightarrow p} f(x) = f(p)
$$
Vale ressaltar que devida a conexão com o conceito de limite, se um função é [[Derivada|derivável]] num dado ponto $x$, isso implica que ela é contínua nesse ponto, entretanto, o inverso não é verdadeiro, uma função pode ser continua num dado ponto mesmo que não seja derivável nesse mesmo ponto.

## Tipos de descontinuidade 
Existem 4 tipos de descontinuidade:
![[tipos de desconinuidade.png]]
