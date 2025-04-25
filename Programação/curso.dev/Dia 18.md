No dia 18, os principais temas abordados  são relacionados a variáveis de ambiente e a gestão e operação do banco de dado PostgreSQL usando `node-postgres`.
# Estrutura básica do `pg`
```javascript
import { Client } from 'pg';

async function query(queryObject){
  try {
    const client = new Client({
      host: "databaseHost",
      port: "databasePort",
      user: "databaseUser",
      database: "databaseName",
      password: "databasePassword"
    });
  
    client.connect();

    const result = await client.query(queryObject);
  } catch (error) {
    console.error(error);
  } finally {
    client.end()
  }
}
```
# Variáveis de ambiente
Um conceito muito interessante é que, para garantir a escalabilidade horizontal de um sistema, ou seja, sua duplicação, triplicação  , ele deve ser *stateless*, sem estado, e esse estado deve ser definido por variáveis externas ao sistema, pertencentes ao ambiente onde sistema está alocado: O ambiente. O módulo mais usado para utilizar as variáveis de ambiente no node é `dotenv`, porém, no [[Dia 3#Next.js|Next.js]] esse módulo já é usado por padrão. 

Normalmente, criamos no nosso projeto um arquivo `.env` para definir as varáveis, porém, esse arquivo raramente é enviado para o repositório remoto, entretanto, o next recomenda o envio desse documento pois define uma hierarquia, começando pelo arquivo `.env.development`, seguindo para `.env` e por último, variáveis injetadas pelo próprio serviço de hospedagem, sendo priorizadas acima de todos os outros, permitindo o uso local de variáveis placeholder para o ambiente de desenvolvimento e o envio do `.env.development` para o repositório remoto.
## Acessando variáveis de ambiente no `compose.yaml`
Adicione o seguinte no seu arquivo `compose.yaml` para permitir o acesso à variáveis de ambiente pelo seu container:
```yaml
env_file:
  - ./caminho/do/seu/.env
```
## Acessando variáveis de ambiente com `dotenv`
```javascript
const variable = process.env.VARIABLE
```
