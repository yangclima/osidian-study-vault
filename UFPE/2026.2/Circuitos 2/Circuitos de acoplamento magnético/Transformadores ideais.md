Um [[Transformadores|transformador]] ideal é um caso específico de transformador que cumpre os seguintes requisitos:

1. As [[Indutores em Circuitos|bobinas]] possuem [[Acoplamento magnético|indutâncias]] muito grandes ($L_1,L_2,M\to \infty$)
2. O coeficiente de acoplamento é $k=1$
3. As bobinas primária e secundária não apresentam perdas

Ou seja, basicamente, **Transformador ideal** é um transformador sem perdas com coeficiente de acoplamento unitário no qual as bobinas primárias e secundária possuem [[Autoindutância|autoindutâncias]] infinitas.

Em geral, esses transformadores são representados utilizando o seguinte esquema:

```tikz
\usepackage{circuitikz}

\begin{document}
\begin{circuitikz}[american]
    % Desenha o transformador no centro (0,0) e dá o nome (T) a ele
    \draw (0,0) node[transformer core] (T) {};

	% Conecta fios aos terminais do primário (Esquerda: A1 e A2)
    \draw (T.A1) to[short, -o, i<=$I_1$] ++(-1,0) node[left] {};
    \draw (T.A2) to[short, -o] ++(-1,0) node[left] {};

    % Conecta fios aos terminais do secundário (Direita: B1 e B2)
    \draw (T.B1) to[short, -o, i=$I_2$] ++(1,0) node[right] {};
    \draw (T.B2) to[short, -o] ++(1,0) node[right] {};
	    
	% Adiciona os textos da relação de espiras (N1 : N2)
    \node at ([xshift=-0.7cm]T.center) {$N_1$}; 
    \node[draw, circle, minimum size=1pt] at ([xshift=-0.7cm, yshift=0.7cm]T.center) {};
    \node at ([xshift=0.7cm]T.center) {$N_2$};
\end{circuitikz}
\end{document}
```

As linhas entre as bobinas representam o núcleo de ferro, responsável pela transmissão integral do [[Fluxo magnético]] do enrolamento primário e secundário, razão do acoplamento magnético ser $1$, os transformadores com núcleo de ferro são boas aproximações dos transformadores ideais.

A característica chave desse tipo de equipamento é então a razão $n = \frac{N_2} {N_1}$ chamada de **Relação de espiras** isso por que utilizando o fator de que não há perdas nesse trafo então utilizando a [[Potência]] nos enrolamentos podemos mostrar que:

$$\frac{V_2}{V_1} = \frac{I_1}{I_2} = \frac{N_2}{N_1} = n $$


Assim, podemos ainda classificar os transformadores utilizando o parâmetro $n$:

- Se $n=1$ trata-se de um transformador isolador
- Se $n>1$ trata-se de um transformador elevador
- Se $n<1$ trata-se de um transformador abaixador

Por outro lado, os valores nominais dos transformadores são normalmente especificados como $V_1/V_2$, assim, para um transformador com valor nominal $2.400/120 \,V$ caso apliquemos $2.400 \,V$ no primário deve surgir no secundário uma [[Potencial elétrico|tensão]] de $120 \,V$.

Note que existe uma certa polaridade associada com o transformador para a qual devemos estar atentos em nossos cálculos, considere então as seguintes relações:

$$\frac{V_2}{V_1} = n \tag{a}$$
$$\frac{I_1}{I_2}= n \tag{b}$$

A relação $(a)$ só é válida quando temos as polaridades $V_1$ e $V_2$ ambas positivas ou ambas negativas com relação ao terminal com o ponto, caso contrário, precisamos substituir $n$ por $-n$ para manter a validade, além disso, a relação $(b)$ só é válida se uma [[Corrente|corrente]] entrar pelo terminal com o ponto e a outra sair pelo terminal com o ponto, caso contrário, precisamos substituir $n$ por $-n$ para manter a validade da equação. Resumindo, as regras são:

1. Se tanto $V_1$ quanto $V_2$ forem positivas ou ambas negativas nos terminais pontuados, use +n na Equação $(a)$. Caso contrário, use $–n$.
2. Se tanto $I_1$ quanto $I_2$ entrarem ou ambos deixarem os terminais pontuados, use $–n$ na Equação $(b)$. Caso contrário, use $+n$.

Lembre-se que não há perdas num transformador ideal, assim, a [[Potência Complexa]] fornecida pelo primário é fornecida ao secundário sem perdas.

$$\hat S_1= \hat V_1\hat I_1^*= \frac{\hat V_2}{n}(n\hat I_1^*)= \hat V_2\hat I_2^*= \hat S_2$$


Podemos então mostrar usando as relações vistas até aqui que:

$$Z_r= \frac{Z_L}{n^2}$$

Isto é, a [[Transformadores lineares|impedância refletida]] do secundário no primário é igual a impedância da carga dividida por $n^2$, de forma similar, podemos refletir fontes de tensão do secundário para o primário dividindo seu valor por $n$ e refletir fontes de corrente do secundário para o primário multiplicando o seu valor por $n$.

Assim, temos:

1. A regra para eliminar o transformador e **refletir o circuito secundário para o lado primário** é: dividir a impedância do secundário por $n^2$, dividir a tensão do secundário por $n$ e multiplicar a corrente do secundário por $n$.
2. A regra para eliminar o transformador e refletir o circuito primário para o lado do **secundário** é: multiplicar a impedância do primário por $n^2$, multiplicar a tensão do primário por $n$ e dividir a corrente do primário por $n$

Note entretanto que isso só se aplica quando temos apenas [[Acoplamento magnético]] entre os enrolamentos, isto é, sem ligações externas entre o primário e o secundário.


