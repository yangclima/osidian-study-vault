A computação e a capacidade de processamento tem crescido exponencialmente nas últimas décadas, pensando nesse sentido, imagine que um dia alcancemos um computador com capacidade infinita de processamento, nesse dia, não precisaríamos mais estudar algoritmos, correto? Na verdade, mesmo nesse caso, provavelmente impossível, estudar algoritmos ainda faria sentido, mesmo que simplesmente para entender se nossos programas terão fim e se finalizarão com a resposta correta mesmo que a engenharia/arquitetura de software (No caso, as boas práticas de desenvolvimento de programas) perca um pouco seu lugar.

Nessa discussão, entramos no escopo de eficiência de algoritmos, afinal, mesmo que os computadores sejam cada vez mais rápidos eles não são infinitamente rápidos, nesse sentido, tempo de processamento tem um custo, memória tem um custo, são recursos limitados e devem ser usados de maneira sensata. Esse uso sensato só é possível usando e estudando os algoritmos.

Na verdade, existe um abismo de diferença entre dois computadores realizando a mesma tarefa mas com algoritmos de diferentes complexidades diferentes, abismo que supera até mesmo diferenças de Hardware.

Suponha dois computadores, o computador $A$, capaz de realizar $10^9$ operações por segundo e um outro, o computador $B$, capaz de realizar $10^6$ operações por segundo (Mil vezes mais lento), ambos tem a tarefa de realizar a ordenação de uma lista de $n$ items, o primeiro utilizando um algoritmo de **Ordenação por inserção** e o segundo um algoritmo de **Ordenação por intercalação**.

O ponto aqui é que o computador $A$ precisará de $c_1\cdot n^2$ operações para ordenar a lista enquanto o computador $B$ precisará de $c_2\cdot \log_2(n)\cdot n$. Sobre as constantes, enquanto os termos de $n$ advém da complexidade do algoritmo, $c_1$ e $c_2$ são constantes que dependem da implementação do algoritmos, arquitetura do computador, eficiência do compilador e da linguagem e etc. assumamos então um cenário pessimista para $B$ com $c_1=2$ (Uma implementação absurdamente eficiente) e $c_2 = 50$, um compilador ineficiente, digamos, nesse sentido, veja que estamos assumindo o pior cenário possível para o computador $B$

Seria uma vitória fácil para $A$ se não conhecêssemos algoritmos, mas se considerarmos uma lista de $n = 10\cdot 10^6$ de itens, nesse caso, enquanto o computador $A$ levaria 5,5 horas para concluir a tarefa, o $B$, mil vezes mais lento em processamento, levaria apenas 20 minutos.

Esse exemplo demonstra por que algoritmos devem ser considerados, tal qual o hardware, uma tecnologia, que, para que se saiba, muitas vezes está presente no nível de aplicação, por exemplo no GPS quando procuramos a melhor rota e em níveis ainda mais baixos, sobretudo se você considerar que até mesmo um projeto de hardware precisa de um algoritmo para ser executado.

# Exercícios:

1. **Cite um exemplo de aplicação que exige conteúdo algorítmico no nível da aplicação e discuta a função dos algoritmos envolvidos**

*R: Um aplicativo de GPS onde é executado um algoritmo cuja função é buscar pela melhor rota entre dois pontos considerando diversos fatores como distância, fluxo de carros e etc.*

2. **Suponha que estamos comparando implementações de ordenação por inserção e ordenação por intercalação na mesma máquina. Para entradas de tamanho $n$, a ordenação por inserção é executada em $8n^2$ passos, enquanto a ordenação por intercalação é executada em $64\cdot n \cdot \log_2 n$ passos. Para quais valores de $n$ a ordenação por inserção supera a ordenação por intercalação?**

*R: As duas funções são crescentes ([[Derivada]] de primeira ordem positiva em todo o domínio) então a ordenação por inserção supera a por intercalação para todos os valores onde $64\cdot \log_2{n} > 8n$ o que equivale aos valores onde $n^8 > 2^{8n}$, ou seja $n \approx 43.55$, ou seja, para todos os valores de $n$ menores que $44$.    
3. **Qual é o menor valor de $n$ tal que um algoritmo cujo tempo de execução é $100n^2$ funciona mais rapidamente que um algoritmo cujo tempo de execução é $2^n$ na mesma máquina?**

*R: $100n^2 < 2^n$ equivale a $\log_2(100)+2\log_2(n) < n$*
