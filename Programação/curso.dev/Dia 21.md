O Dia 21, aborda questões relativas à criação e manutenção do [[Dia 17#Banco de dados|Banco de dados]] no ambiente de produção. 
# Banco de dados como commoditie
Para utilizar um banco de dados em produção, a forma mais simples é utilizar provedores desse serviço, bons exemplos são Neon e Tembo (gratuitos com limitações) e DigitalOcean (Pago), porém, o banco de dados não passa de uma *commoditie*, um serviço padronizado entre diferentes provedores, distinguindo apenas em questões como a quantidade de conexões simultâneas e a localização geográfica do servidor. Um BD PostgreSQL funciona igual a qualquer outro BD PostgreSQL independente de que servidor esteja o hospedando.

Dito isso, precisamos construir a nossa aplicação evitando ao máximo o *vendor lock*, ou seja, de forma que ela seja independente de quem está nos prestando um serviço.

As duas principais maneiras de gerir e implementar a infraestrutura do seu sistema é utilizando *ClickOps* ou *IaC*.
# Connection string PostgreSQL
Para se conectar através de algumas interfaces Postgres, como `psql`, `node-pg-migrate` ou `node-pg` pode ser viável e prático, ao invés de utilizar props (`username`, `pasword`,  `dbName` e etc.) utilizar uma connection string, no seguinte formato:
```
postgres://<username>:<password>@<database_url>:<port>/<database_name>
```
# Integrando BD de produção que exige SSL
SSL ou Secure Sockets Layer é um protocolo de cyber segurança utilizado para garantir a comunicação segura entre dois dispositivos conectados na internet, alguns provedores de serviços de BD exigem a utilização de SSL na conexão, tornando necessário utilizar `ssl: true` no cliente `pg` e às vezes adicionar um certificado do provedor na sua API o que exige utilizar `ssl: {ca: <certificado>}`, para continuar utilizando o BD local sem problemas é conveniente utilizar uma função `getSSLValues` que retorne o valor do certificado com base no ambiente utilizado.