O Redis é um banco de dados em memória usado popularmente como banco de dados, cache ou message broker.

Seguindo a mesma ideia de outros bancos de dados não relacionais, ele permite o armazenamento de grandes quantidades de dados sem do usuário sem apresenta a rigidez estrutural de uma [[Introdução e o modelo relacional|base de dados relacional]] e permitindo múltiplos formatos e estruturas de dados.

Quanto a arquitetura o Redis possui, em geral, um servidor e um console client, podendo ainda ser estruturado com uma estrutura master-slave para suportar um fluxo de dados maior.

O ponto chave aqui, a grande vantagem do Redis é sua velocidade absurdamente alta, persistência de dados com changes salvas assincronamente em disco, o próprio suporte a diferentes tipos de dados e a atomicidade que se espera de um sistema desse tipo

Para usar o redis no windows o mais fácil é usar o docker, como o comando:

```bash
docker run -d --name redis -p 6379:6379 redis:<version>
```

Ou usando um arquivo `compose.yaml`:

```yaml
version: '3.8'

services:
  redis:
    image: redis:alpine
    container_name: meu_redis
    ports:
      - "6379:6379"
    volumes:
      - redis_data:/data
    command: redis-server --appendonly yes

volumes:
  redis_data:
```

Para entrar no container e acessar a interface de linha de comando do Redis, usamos:

```bash
docker exec -it redis redis-cli
```
