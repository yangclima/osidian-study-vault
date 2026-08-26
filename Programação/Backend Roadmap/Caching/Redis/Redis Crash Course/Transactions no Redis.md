O Redis oferece ainda suporte a transações, garantindo a atomicidade como pedem os [[Princípios ACID]], para iniciar uma transaction, usamos:

```bash
multi
```

Em seguida, digitamos todos os comandos e operações que constituem a transação, recebendo "QUEUED" após cada um, em seguida, para executar, usamos então:

```bash
exec
```

Ou, caso queiramos cancelar a operação:

```bash
discard
```

Nesse contexto, temos também o comando `watch`, usado para observar um valor no Redis, basicamente dizemos para o Redis verificar alterações num valor:

```bash
watch <chave>
```

Em seguida fazemos uma transação qualquer, se a variável citada no watch tiver sido modificada a transação falhará, caso contrário, terá sucesso.