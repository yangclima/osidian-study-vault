O **Pub/Sub (Publicação/Assinatura)** no Redis é um mecanismo de mensageria em tempo real onde remetentes (**publishers**) enviam mensagens para canais específicos, e destinatários (**subscribers**) recebem essas mensagens instantaneamente. Ele permite a comunicação assíncrona entre microsserviços e sistemas sem que eles precisem se conhecer diretamente. 

Para qualquer um conectado ao Redis se inscrever num canal, passar a observar mensagens enviadas nele, usamos:

```
subscribe <canal[]>
```

Ou para receber mensagens em qualquer canal que obedeça a uma pattern regex, usamos:

```bash
psubscribe <pattern[]>
```

E para qualquer outro enviar mensagens em um canal usamos:

```bash
publish <canal> <mensagem>
```

Para ver os canais abertos (Não inclui canais declarados por patterns regex):

```bash
pubsub channels
```

Para incluir patterns regex declaradas:

```bash
pubsub numpat
```

E para ver o número de subscriptions para um canal:

```bash
pubsub numsub <canal>
```