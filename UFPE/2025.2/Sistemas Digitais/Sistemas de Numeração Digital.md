Os [[Sistemas Digitais|Sistemas digitais]], representam quantidades de maneira discreta através dos sistemas de numeração. Devido a conveniência no cotidiano humano surgiu naturalmente o sistema de numeração decimal, devido a quantidade de dedos em nossas mãos.
# Sistema de numeração decimal
Os sistema de numeração decimal é construído utilizando-se de 10 símbolos distintos: 1, 2, 3, 4, 5, 6, 7, 8 e 9, que arranjados em conjuntos sequenciais podem ser utilizados para representar qualquer quantidade, 237, por exemplo, onde o 2 vale, na verdade *2 centenas*, o 3 vale *3 dezenas* e de fato, o 7 vale *7 unidades*, percebemos então um padrão: cada número $k$ num arranjo numérico representa o valor de $k\cdot10^p$ onde $p$ é sua posição no arranjo (Começando do 0). Além disso, utilizamos a vírgula como sinal para separar valores positivos das potências e os valores negativos. O valor que cada posição representa damos o nome de peso ($10^p$, além disso, chamamos a casa decimal mais a esquerda de **Dígito mais significativo** (No inglês MSD) e a casa decimal mais a direita de **Dígito menos significativo** (No inglês LSD).

![[sd02.png|center]]

Com $N$ casas decimais é possível representar $10^N$ valores.
# Sistema binário
Em sistemas digitais, porém, não é viável utilizar 10 símbolos, seria algo como definir 10 estados possíveis de tensão num sinal elétrico, por isso, utiliza-se o sistema binário simplificando a compreensão e estruturação desses sistemas utilizando-se ligado-desligado ou faixas bem mais extensas de tensão. O sistema binário segue a mesma lógica, só que na base $2$, um valor $k$ na posição $p$ tem valor $k \cdot 2^p$ e utilizando $N$ casas decimais (Bits) é possível representar $2^N$ valores distintos.

![[sd03.png|center]]

![[sd04.png|center]]

# Sistema Hexadecimal
Existe ainda um sistema de numeração na base 16, o sistema Hexadecimal que utiliza os dígitos de 0 a 9 e os caracteres A, B, C, D, E e F para expressar os valores, seguindo a mesma lógica dos outros dois sistemas que vimos, com $N$ dígitos podemos representar uma faixa de $0$ a $16^N - 1$ valores e um dígito $x$ na posição $n$ - Da direita para a esquerda - representa o valor de $x \cdot 16^n$ .