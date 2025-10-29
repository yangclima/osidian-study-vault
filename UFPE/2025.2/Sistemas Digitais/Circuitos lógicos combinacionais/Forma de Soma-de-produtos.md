O projeto e desenvolvimento de [[Introdução a 1s e 0s digitais|Sistemas digitais]], em geral, envolve a utilização de múltiplas portas [[Operação NOT|NOT]], [[Operação AND|AND]], e [[Operação OR|OR]] para gerar os mais diversos tipos de comportamento, nesse sentido é necessário que tenhamos sólidos métodos de simplificação de circuitos e [[Descrevendo Circuitos Lógicos Algebricamente|expressões booleanas]] para que possamos obter circuitos digitais tão simples quanto possíveis.

A maior parte dos métodos de simplificação que possuímos envolvem trabalhar com expressões que estão na forma de **Soma-de-produtos**, dizemos que uma expressão booleana está nessa forma quando ela é **composta pela soma de vários termos onde cada termo é um produto de duas ou mais variáveis negadas *individualmente* ou não negadas** ($A\bar B$ é um termo válido, porém, $\overline{AB}$ não é).

A grande vantagem da soma de produtos é poder encontrar termos que se anulem de tal forma que a forma mais simples de um circuito sempre será uma soma-de-produtos.

Uma outra forma geral de escrever expressões booleanas é a forma de produto de somas.