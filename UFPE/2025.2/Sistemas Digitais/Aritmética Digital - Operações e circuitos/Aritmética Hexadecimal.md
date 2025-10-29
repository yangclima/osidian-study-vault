Além das operações de [[Adição e Subtração Binária]], [[Multiplicação de números binários]], [[Divisão binária]] e [[Adição em BCD]], podemos também realizar operações aritméticas num [[Sistema de numeração hexadecimal]].

Nesse sistema de numeração, a soma pode ser efetuada de maneira simples, seguindo os seguintes passos:
1. Some os dois dígitos em hexadecimal
2. Se a soma for menor ou igual a $15$ ela pode ser expressa como um dígito hexadecimal
3. Se a soma for maior que $15$, subtraia $16$ para obter o resultado e passe  um *carry* equivalente para o próximo dígito

Por outro lado, ao realizar a subtração, lembre-se que os números hexadecimais são só uma forma mais simples de representar os números binários, dessa maneira, podemos realizar realizar a sua subtração a partir da sua conversão em binários. Uma forma mais simples de fazer isso é fazer uma espécie de [[Representação de números com sinal|complemento de 2]] hexadecimal e consiste em subtrair o seu número do equivalente de mesma quantidade de dígitos composto apenas por $F$ e depois somar $1$:

![[sd_013.png|center]]

Além disso, perceba que para a representação de binários com sinal, devido ao bit de sinal podemos chegar a conclusão de que, nesse sistema de representação, se o MSD do hexadecimal for maior ou igual a $8$ ele será negativo, caso contrário, será positivo.