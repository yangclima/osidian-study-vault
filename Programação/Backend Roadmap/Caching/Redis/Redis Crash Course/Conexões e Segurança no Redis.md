O Redis oferece alguns comandos para verificar a conexão e segurança do servidor.

Para verificar se a conexão está estabelecida, usamos:

```bash
ping
```

Se a conexão estiver correta o servidor responderá com `PONG`, também podemos usar o comando:

```bash
echo <message>
```

Se o servidor responder com `<message>` você confirma não só que a conexão TCP/TLS está aberta, mas que a camada de protocolo está lendo e respondendo corretamente sem corrupção de dados.

Além disso o Redis permite a existência mútua de vários bancos de dados com diferentes namespaces no mesmo servidor, por padrão o banco ativo é o de índice 0, mas podemos alternar entre bancos usando:

```bash
select <index>
```

Para ver os clients disponíveis, usamos:

```bash
client list
```

E para nomear um client:

```bash
client setname <name>
```

Para matar um client através do id:

```bash
client kill id <id>
```

Para adicionar uma senha ao servidor, usamos:

```bash
config set requirepass <senha>
```