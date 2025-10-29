Quando representamos um número ou letra por um conjunto especial de símbolos, dizemos que este está codificado, neste caso, chamamos de código o tal conjunto de símbolos.

Utilizando essa ideia de código, podemos representar os números do [[Sistemas de numeração digital|sistema de numeração decimal]] no sistema binário sem necessariamente realizar uma conversão numérica dos valores, isso é possível utilizando o código **BCD** (*Binary Coded Decimal*) ou **Decimal Codificado em binário**, nesse tipo de codificação cada número decimal é representado por um conjunto de $4$ dígitos binários, por exemplo:

> O número $456$ pode ser codificado como $0100-0101-0110$ já que $4$ equivale a $0100$, $5$ equivale a $0101$ e $6$ a $0110$.

A conversão de BCD para decimal é similar a [[Sistema de numeração hexadecimal|conversão de hexadecimal para binário]], pegamos cada conjunto de $4$ dígitos e convertemos para decimal, por exemplo:

> O número $1001-1000-0111$ em BCD equivale, em decimal, a $987$ já que $1001$ equivale a $9$, $1000$ equivale a $8$ e $0111$ equivale a $7$.

Perceba que nesse caso, existem valores inválidos, como $1111$, $1110$ e outros, o que implica numa menor eficiência do sistema BCD com relação ao sistema binário, com $4$ dígitos em binário podemos representar do $0$ ao $15$, porém, em BCD só conseguimos representar do $0$ ao $9$.