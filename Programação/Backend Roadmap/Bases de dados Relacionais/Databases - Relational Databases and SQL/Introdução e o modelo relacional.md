Um DBMS (Database Management System) é um sistema que provê o eficiente, confiável, conveniente e seguro armazenamento e acesso multiusuário de dados persistentes.

Para desempenhar esse papel, os DBMS operam sob dados dispostos usando os chamados Data Models, que nada mais são que descrições de como, em geral, os dados são estruturados, temos, por exemplo, o modelo relacional, o graph e o não relacional.

Nesse sentido, surgem ainda os conceitos de Schema (Definido usando DDL - Data Definition Language) e Data (Acessados e alterados usando DML - Data Manipulation Language), o primeiro funcionando como a própria estrutura dos dados, algo como uma tipagem dos mesmos e o segundo como os dados armazenados propriamente ditos.

Por trás da construção desses sistemas, se destacam 4 papéis:
1. DBMS Implementer - Responsável por construir o DBMS
2. Database Designer - Responsável pela definição do Schema
3. Database Application Developer - Responsável pela construção dos programas que operam sobre o o Database
4. Database Admin - Responsável pela administração dos dados 

O nosso foco inicial será no modelo relacional, o mais maduro dos modelos, com 35 anos e largamente presente na maioria das aplicações comerciais de banco de dados. O que se destaca nesse modelo é a sua simplicidade, que permite que ele seja operado por linguagens de alto nível e o fato de existirem implementações extremamente eficientes desse modelo. 

Dentro do contexto do modelo relacional, uma Database é nada mais do que um conjunto de relações (Tabelas) nomeadas, cada uma das quais possui um conjunto de atributos (Colunas)que possuem tipos e são nomeados, e é populada por tuplas (Linhas) que possuem um valor para cada um desses atributos, nesse sentido, se destaca ainda o conceito de Key, ou atributo chave, um atributo (Ou conjunto de atributos) de um linha cujo valor é único entre todas as linhas e é usado para representar de maneira unívoca a linha e são usados para a realização de consultas mais rápidas e também para definir relações entre linhas.

Além disso, temos ainda o conceito já antes mencionado de Schema que aqui existe como uma descrição estrutural da relações além do conceito de instância que designa o conteúdo atual de uma database num determinado instante do tempo.

Definidas as primitivas, o passo a passo para criar e usar um database relacional é o seguinte:

1. Defina um Schema usando Data Definition Language
2. Popule o seu banco de dados
3. Repita, realize buscas e modificações

As buscas e modificações, conhecidas como queries são feitas usando DML mas que é tomada com sinônimo de query language, exemplos de query languages são a Algebra relacional e o SQL, sendo a primeira extremamente formal e a segunda extremamente simples, mas fundamentada completamente na primeira.

A grande vantagem das query languages e do modelo relacional é que as queries são fechadas, ou seja, retornam apenas relações e são também composicionais, o que significa que é possível executar queries sobre o resultado de outras queries. 