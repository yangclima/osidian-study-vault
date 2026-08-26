> https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/What_is_a_domain_name

Como vimos em [[Como a internet funciona]], todos os computadores são identificados na rede e os pacotes são roteados através dos endereços IP, sejam IPv4 ou IPv6, porém, apesar desses endereços serem fáceis de lidar para os computadores, é difícil para os humanos lembrá-los e identificar quem os detém e o que roda no servidor, por isso os nomes de domínios são parte chave da infraestrutura de rede.

A forma padrão desses nomes de domínio é a seguinte:

```
labeln.[...].label2.label1.tld
```

Cada `label` fornece uma informação específica sobre o nome de domínio ou serviço que ele hospeda.

O `tld` (Top Level Domain) serve para mostrar pro usuário o propósito geral do serviço designado por aquele nome de domínio e pertence a uma lista restrita e controlada pela ICANN (Internet Corporation for Assigned Names and Numbers), alguns deles mais genéricos e permissivos, como `.com`, `.net` ou `.org` e outros os quais você precisa atender alguns requisitos mais ou menos controlados para deter, por exemplo:

- TLDs locais como `.br`, `.us` ou `.fr` requerem que o serviço hospedado para o qual aponta ao nome de domínio ou seja hospedado no país referente ou que o recurso que ele hospeda seja numa língua desse país
- O TLD `.gov` é permitido apenas para organizações governamentais
- O TLD `.edu` só é permitido para instituições educacionais

Os TLDs podem conter tanto caracteres especiais como latinos e tem no máximo 63 caracteres.

Os Labels que seguem o `tld` são formados por sequências case-insensitive de caracteres de ``A`` a ``Z``, números de ``0`` a ``9`` e caracteres `-`, sendo que o caractere `-` não pode ser usado no primeiro nem no último caractere do label.

Um nome de domínio pode então ter vários labels, apesar de não ser de nenhuma forma obrigatório uma quantidade específica de nomes, além disso, se você é detendo de `domain.org` por exemplo você pode criar subdomínios como `subdomain.domain.org` ou `subsubdemain.subdomain.domain.org` e etc.

Para ter controle de um nome de domínio você não pode comprá-lo, se assim fosse, com o tempo um número cada vez maior de domínios ficaria indisponível permanentemente, por isso, o  que ocorre é que você paga pelo direito de utilizar um determinado domínio por um tempo de um ou mais anos e sua renovação tem prioridade sob solicitações de outras pessoas de modo que se um domínio deixa de ser usado, muito em breve ele se tornará disponível para que outra pessoa usufrua dele.

Essa compra de direitos é intermediada por companhias chamadas `registrars` que utilizam registros de nome de domínio para manter as informações técnicas e administrativas que te conectam ao seu domínio.

É possível verificar a disponibilidade de um domínio usando o comando:

```cmd
whois <domain_name>
```

Que no windows precisa ser [instalado](https://learn.microsoft.com/pt-br/sysinternals/downloads/whois).

Uma vez que você compra os direitos do domínio ou que, atualiza algum dos registros de um domínio que você possui, esses dados não são uniformemente atualizados, isso ocorre por quê as informações do DNS são distribuídas e controladas por alguns servidores especiais denominados Authoritative Name Servers ou Top-Level DNS servers então para que as informações sejam atualizadas na internet toda você precisa esperar que os dados nesses servidores expirem e eles atualizem os dados.

Basicamente, o workflow ao digitar um nome de domínio no navegador é o seguinte:

1. O navegador verifica no ambiente local se o computador conhece o nome de domínio, se ele conhecer, transforma em IP e faz a requisição
2. Se não conhecer, faz uma requisição de resolução de DNS a um server DNS e obtém o IP do referido nome de domínio
3. Faz a [[O que é HTTP|requisição]] usando o IP obtido
