Não é segredo que os bancos de dados [[Introdução e o modelo relacional|relacionais]] foram revolucionários desde sua invenção em  meados de 1970 e que desde lá tem sido base para o estabelecimento e manutenção das mais variadas indústrias e setores, apesar disso, é essencial que conheçamos suas principais vantagens e desvantagens tanto para entender seus limite quanto para justificar sua aplicação.

As suas principais vantagens são:

1. **Estrutura**: Esses sistemas organizam os dados de forma estruturada e consistente, facilitando o acesso, recuperação e manipulação dos dados.
2. **Integridade**: Eles fornecem múltiplas ferramentas para garantir a integridade dos dados, em especial, todas as [[Constraints]], prevenindo, à demanda, o armazenamento de dados semanticamente desconexos
3. **Relações**: Eles permitem definir e gerenciar [[Relações básicas entre tabelas|relacionamento entre dados]] usando chaves primárias e estrangeiras facilitando a busca análise de informações relacionadas.
4. **Consultas e relatórios:** Eles disponibilizam poderosas linguagens de query, como o SQL que funcionam como formas fáceis e concisas de buscar e alterar dados tornando muito simples a tarefas de gerar relatórios e obter insights a partir dos dados.
5. **Segurança**: Durante a sua evolução, os RDBMS ganharam poderosos mecanismos de segurança e gestão de acesso aos dados armazenados.
6. **Escalabilidade**: Eles podem receber grandes quantidades de dados e serem escalados para acomodar o crescimento de aplicações e plataformas, com opções modernas de clustering e alta disponibilidade
7. **Transações e ACID**: Eles possuem um robusto padrão de [[Transactions]] e [[Princípios ACID]] que atuam como premissas de disponibilidade, concorrência e confiabilidade de dados
8. **Backup**: Eles fornecem formas simples e aplicáveis de realizar backups periódicos e eventual recuperação de dados, como o [[Write-Ahead Logging]]
9. **Indexação**: Eles fornecem poderosas ferramentas de indexação que permitem uma cesso rápido e eficiente aos dados de uma relação.
10. **Normalização**: Eles incentivam a normalização de dados, evitando redundâncias e provendo eficiência de acesso, modificação e armazenamento.
11. **Padrão da Indústria**: Esses sistemas são o padrão da indústria e por isso estão em constante desenvolvimento e atualização além de terem claramente se provado como soluções eficientes e confiáveis
12. **Consistência**: Eles tem diversas features que garantem a consistência relacional dos dados evitando erros de relacionamento e validade dos dados
13. **Independência dos dados:** Esses sistemas são abstrações extremamente bem feitas de forma que a sua implementação física é totalmente isolada de sua implementação lógica o que reduz os custos de manutenção e permite que diversos parâmetros da base de dados sejam alterados sem mudar a aplicação que roda sobre ela.
14. **Acessibilidade**: Esses bancos, através de implementações como o [[Controle de Concorrência Multi Versão]] permitem múltiplos acessos independentes e simultâneos sem comprometer a estrutura dos dados

Enquanto as principais desvantagens são:

1. **Limitações de Escalabilidade**: Em escalas gigantescas se torna complexo expandir eficientemente esses bancos de dados e sua performance pode decair
2. **Design Complexo**: Projetar um RDBMS pode ser complexo, em especial para aplicações com regras de negócios complicadas e requer uma certa expertise
3. **Esquema Fixo**: Em alguns casos, os [[Schemas]] predeterminados podem gerar problemas na evolução de uma aplicação, sobretudo quando termos mudanças necessárias não planejadas
4. **Gargalos:** Algumas operações complexas nessas bases de dados, como alguns joins podem se tornar gargalos em larga escala e precisam ser tratados com índices e outras otimizações
5. **Custo operacional**: Eles tem, tipicamente, um custo operacional mais alto devido a normalização, transações e integridade referencial quando comparados com bancos de dados não relacionais, resultando em um overhead de armazenamento e queda de performance
6. **Custos**: Alguns RDBMS desse tipo podem ser razoavelmente mais caros em larga escala que outras soluções de bancos de dados
7. **Complexidade de Replicação**: Ao contrário dos bancos não relacionais modernos, o s relacionais não nasceram para o modelo distribuído então soluções de clustering para esses RDBMS costumam ser mais complexas 
8. **Ponto de falha único**: Enquanto replicar esses bancos é complicado, usar eles da forma tradicional tem como desvantagem o clássico problema de **Single Point of Failure**
9. **Desafios de modelagem de dados**: Modelar certos tipos de dados, como dados hierárquicos ou desestruturados pode ser complexos em bancos de dados relacionais
10. **Problemas de concorrência**: Em larga escala, manipular transações concorrentes pode ser muito complexo e formar um gargalo de escalabilidade
11. **Curva de aprendizado**: Bancos relacionais tem uma curva de aprendizado muito mais íngreme
12. **Rigidez**: Como alterar a estrutura desses bancos consome tempo e processamento suas estruturas são muito mais rígidas e inflexíveis