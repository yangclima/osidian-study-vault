No nosso estudo a respeito da mecânica dos fluidos já vimos alguns conceitos relacionados a [[Hidrostática]], uma subárea da própria mecânica dos fluidos que consiste no estudo de fluidos em repouso, o próximo passo é começar a trabalhar com fluidos em movimento, considerar fluidos submetidos a velocidades e acelerações, a Hidrodinâmica.

# Fatores de simplificação
Para estudar o comportamento dos fluidos sem a necessidade de uma base extremamente profunda a respeito do cálculo e álgebra linear é preciso levar em consideração alguns efeitos simplificadores, considerações que visam tirar de jogo algumas complexidades permitindo um cálculo mais simples de algumas propriedades, para isso assumimos que estamos trabalhando com um **Fluido Ideal**, um fluido que possui as seguintes propriedades:
1. **Sem viscosidade:** Assumimos que não existe atrito entre as moléculas do fluido, ou seja, que ele não é viscoso.
2. **Irrotacional:** Consideramos que os elementos do fluido não giram em torno de seus próprios centros de massa.
3. **Escoamento laminar:** Consideramos que o escoamento do fluido é laminar, ou seja, o vetor velocidade em um ponto específico do fluido é constante.
4. **Incompressível**: Consideramos que o fluido tem densidade fixa, é incompressível

# Equação de continuidade
![[hidrodinamica-01.png]]

A primeiro relação importante da hidrodinâmica é a **Equação de Continuidade**, que consiste basicamente numa relação matemática entre a área da secção transversal na qual o fluido escoa e sua velocidade de escoamento, o efeito dessa relação pode ser visto ao, por exemplo, reduzir a secção transversal de uma mangueira e notar que as velocidade de escoamento do fluido aumenta, a relação pode ser escrita como:
$$
A_1V_1 = A_2V_2
$$
Ou seja, o produto da secção transversal na qual um fluido escoa pela sua velocidade de escoamento é constante.