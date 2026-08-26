# Fonte 01
> https://en.wikipedia.org/wiki/Schema_migration

Na engenharia de software, uma `Schema Migration` se refere ao gerenciamento de alterações controladas por versão, incrementais, e às vezes reversíveis nos schemas de bases de dados relacionais.

Essas migrações são aplicadas de forma programática usando uma ferramenta de migração que aplica ou reverte essas migrations sucessivamente para alcançar uma determinada versão do schema do [[Databases - Relational Databases and SQL (Stanford)|banco de dados]] .

O grande objetivo dessas ferramentas é permitir a evolução do schema do db com um impacto mínimo sobre os dados nele armazenado, no entanto, o impacto zero nunca é garantido, já que, por exemplo, uma migration que remove uma coluna de uma tabela promove um perda dos dados dessas tabela que não podem ser restaurados.

Essas migrations então compõem uma parte essencial da evolução do software e permitem que o schema do banco de dados evolua com as demandas que eventualmente surgem durante o crescimento de uma aplicação, entretanto, aplicar migrações numa db de produção sempre oferece riscos, que podem ser minimizados utilizando estratégias como databases de teste e homologação, execução em dry run e etc., apesar de, mais uma vez, o risco nunca ser zero.

Existem diversas estratégias para mitigar algumas dificuldades relacionadas a aplicação de migrações, chamadas `Migration Strategies`, a estratégia clássica, uma vez que as aplicações que rodam sobre a db só conseguem enxergar uma versão do schema por vez, é simplesmente parar a aplicação , aplicar as migrações e então rodar a aplicação novamente, no entanto, isso gera um tempo de downtime que, por vezes, não é tolerável, nesse sentido surgem algumas outras estratégias:

- **Dual Writing:** Essa estratégia consiste em modificar o schema de tal modo que ele suporte os dados tanto na versão antiga como na nova, fazer o deploy da aplicação de tal modo que ela escreva os dados em ambas as versões simultaneamente, realize um backfill no db copiando os dados que já existiam antes da migration para o novo formato e então faça o deploy de uma nova versão do aplicação que lê o novo formato dos dados e para de escrever nos dois formatos, por fim, removemos os dados no formato antigo
- **Dual reading:** Tal qual o dual writing, modificamos o db para suportar dados tanto no formato antigo como no novo, mas fazemos o deploy de uma versão da aplicação capaz de ler os dados em ambos os formatos simultaneamente, mas que escreve os dados apenas no novo formato, em seguida, realizamos um backfill capaz de atualizar os registros antigos para o novo formato, fazemos o deploy de uma aplicação que lê os dados apenas no novo formato e por fim deletamos os registros no formato antigo
- **Dual Reading and Writing:** Usando as duas últimas estratégias combinadas teremos uma aplicação capaz de funcionar normalmente com ambos os formatos (Antigo e Novo) de modo que o backfill poderá ser realizado gradualmente e fazendo o uso de feature flags.

# Fonte 02
> https://www.mongodb.com/resources/basics/databases/database-migration

Imagine o problema de mudar a sede de um empresa, perceba que não se trata simplesmente de mover as mesas e cadeiras de um prédio para outro, mas de algo muito mais complexo, é sobre garantir o funcionamento de tudo, garantir que o fluxo de trabalho continue funcionando na nova sede, que os computadores serão configurados corretamente, que todos os documentos não saiam da ordem ao transferir o armário de um lugar para outro e muitas outras minúcias, esse mesmo problema surge ao lidarmos com bases de dados.

A maioria das aplicações rodam sobre algum tipo de [[Databases - Relational Databases and SQL (Stanford)|base de dados]], mas as tecnologias usadas evoluem rapidamente do mesmo modo que os requisitos funcionais também evoluem, por isso, quase sempre teremos que lidar com a tal mudança de sede, transferir a DB de servidor, mudar o seu Schema, permitir que o sistema escale horizontal e verticalmente, garantir a sua performance são alguns exemplos dessas "mudanças", feitas aqui, por meio das chamadas Migrations, que, se bem executadas, garantirão que nenhum dado seja perdido e que o tempo de downtime seja mínimo.

O conceito de migration surgiu naturalmente no campo de desenvolvimento de software primeiro quando as empresas precisaram transferir os dados dos antigos arquivos de papel para os primeiros SGBD's, posteriormente a mesma necessidade apareceu com relação a transferência de dados entre diferentes tecnologias ou softwares proprietários e posteriormente para a transferência para os serviços de cloud, por fim, a demanda por sistemas de migração se concentram no desenvolvimento de ferramentas cada vez mais eficientes, rápidas e seguras.

Aqui, diferente das Schema Migrations, estamos tratando propriamente de migrações de bases de dados, que se referem a completa reestruturação da DB e seu schema numa outra plataforma ou sistema, otimizando queries, garantindo o atendimento das regras de negócio e a integridade dos dados.

Existem 4 tipos principais de Migrations de dados:

1. **Storage Migrations:** Envolve a transferência dos dados de um sistema de armazenamento para outro e envolve algumas considerações chave: Compatibilidade do formato de dados, melhoria da performance, integridade dos dados e minimização do downtime.
2. **Database migrations:** Envolve a transferência de uma database de uma fonte para um alvo, como mudar o DBMS ou atualizar o atual, são pontos chave aqui: Migração de Schema, Consistência dos Dados, Estratégias de migração, Teste e Validação.
3. **Application Migration:** Envolve a transferência da aplicação como um todo, junto com seus sistemas de bancos de dados para um novo ambiente, nesse cenário, os principais desafios são: Modificações do schema da DB, as dependências da aplicação, otimizações de performance e a experiência do usuário final.
4. **Cloud Migration:** Envolve a transferência de DB's e serviços alocados em servidores locais para serviços de nuvem, como AWS, Google Cloud, Azure e outros, nesse caso, os principais aspectos são: A escolha entre os modelos de cloud (Privada, pública ou Hibrida), Serviços nativos da nuvem, segurança e conformidade e estratégias de migração.

Quanto as principais estratégias de migração, temos:

1. **Big Bang DB Migration:** A migração é feita de uma só vez, em uma operação, exigindo um downtime mas possuindo uma transição mais rápida.
2. **Trickle DB Migration:** Os dados são transferidos gradualmente enquanto o source e o target rodam simultaneamente, o downtime é menor mas o processo de transição é mais extenso.
3. **Zero Downtime DB Migration:** Estratégias de replicação e/ou redirecionamento são usadas de modo que o downtime é zero mas geralmente a transição é bem mais complexa.

Alguns dos principais motivos para uma operação complexa e potencialmente arriscada como uma migração de database ser realmente desejável são: 

1. O acesso a features mais avançadas de DB em uma versão mais recente do seu DBMS ou em outro DBMS, como uma melhor indexação e otimização de query, medidas de segurança mais avançadas, escalabilidade automática ou um suporte melhor para sistemas distribuídos
2. Mesclar múltiplas bases de dados, para objetivos como a diminuição da latência entre operações, facilidade na análise de dados e menos overhead administrativo
3. Reduzir os custos operacionais, minimizando despesas com infraestrutura, profissionais de TI, melhores modelos de pricing e etc.
4. Adicionar ou melhorar os sistemas de redundância e recuperação de desastres, por exemplo através da criação de réplicas geograficamente distribuídas ou arquiteturas que evitam problemas de Single Point of Failure
5. Melhorar a segurança e conformidade, pro exemplo através de algoritmos mais modernos de criptografia, autenticação multi fator, features como role-based access entre outros

A importância do uso e do correto uso de migrações reside também nos riscos associados a realização de migrações de maneira imprópria, trazendo problemas como perda de dados, problemas de compatibilidade, aumento do downtime e aumento de custos operacionais.

Quanto a factual aplicação da migração de database, para realizá-la, primeiro acessamos a DB fonte analisando potenciais riscos e problemas, analisando a estrutura do banco, o volume de dados e sua complexidade, potenciais problemas de compatibilidade e gargalos de acesso, aproveitando a oportunidade para melhorar o desempenho. Em seguida, selecionamos um ferramenta conveniente de migração, definimos regras de qualificação dos dados, executamos a migração de schema, executamos a migração dos dados e por fim, testamos e otimizamos a database.





 