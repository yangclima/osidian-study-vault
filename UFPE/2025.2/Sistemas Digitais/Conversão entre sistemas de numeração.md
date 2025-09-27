Uma problema recorrente ao lidar com sistemas digitais é a necessidade constante de realizar conversões entre os [[Sistemas de Numeração Digital]], usualmente, os dispositivos costumam trabalhar no sistema de numeração binário, que faz muito mais sentido nesse contexto, mas, no entanto, é muito menos inteligível para nós humanos, existem então, técnicas que permitem transitar e converter valores espressos num determinado sistema e expressá-los em outro.

# De outro sistema para decimal
Como sabemos, $x_n$ o $n$-ésimo dígito - Da direita para a esquerda - de um valor expresso no sistema de numeração de base $B$ tem valor $x_n \cdot B^n$ portanto, para converter um valor de $k$ dígitos desse sistema para o sistema decimal, basta realizar o seguinte somatório:
$$
\sum_n^k x_n \cdot B^n 
$$

# Do sistema decimal para outro sistema
Para converter do sistema decimal para outro sistema o processo é um pouco diferente, apesar de ser bem mecânico, e consiste no seguinte:
você deve realizar sucessivas divisões do valor pela base do outro sistema, anotando o quociente e o resto, até que o quociente seja 0, então, o n-ésimo resto - Na ordem em que foram obtidos - será o n-ésimo valor - Da direita para a esquerda - do número no outro sistema.