Desde o início do projeto até o [[Dia 33]] desenvolvemos uma sólida fundação para o nosso projeto, faltando apenas "lamber" o que criamos até agora, ou seja, refatorar e revisar as implementações de maneira a encontrar erros e possíveis problemas futuros.

O primeiro passo é então checar possíveis atualizações nas dependências do nosso projeto. 

No ecossistema  do `node` com o `npm`, os criadores dos pacotes podem reportar possíveis vulnerabilidades encontradas em seus pacotes para avisar os desenvolvedores de projetos que utilizam esses pacotes como dependências, da existência desses problemas para que eles possam evitar tais vulnerabilidades e ocasionalmente atualizar os pacotes evitando expor-se a essas brechas, o `npm`, por padrão, já faz essa checagem ao instalar um pacote, mas podemos fazê-la por conta própria com o comando:

```bash
npm audit
```

no entanto, o sistema de auditoria do `npm` é conhecido por muitos falsos positivos, por exemplo, quando expõe como críticas as vulnerabilidades das dependências de desenvolvimento, que não poderiam ser exploradas sem acesso ao ambiente local do servidor, por isso, podemos adicionar algumas flags ao nosso comando:

```bash
npm audit --omit=dev --audit-level=critical
```

Onde `--omit=dev` oculta vulnerabilidades das dependências de desenvolvimento e `--audit-level=critical` que oculta alertas de vulnerabilidade de nível `low`, `moderate` e `high`, mas retorna um status code maior que 0 quando alguma vulnerabilidade crítica é apontada, o que pode ser integrado ao nosso [[Dia 29#Implementando Continuous Integration|CI]] nas nossas [[Dia 31#GitHub Actions|GitHub Actions]].

O sistemas de versionamento dos pacotes `npm` seguem o chamado `SemVer` ou `Semantic Versioning`, no qual, a versão de um pacote é constituída de três números, possuindo a seguinte estrutura:

```
[major].[minor].[patch]
```

Onde atualizações `patch` são atualizações de correção, performance, refatoração... mas que não apresentam nem novas features nem `BREAKING CHANGES`. 

Atualizações `minor` são atualizações com novas features mas que também não apresentam `BREAKING CHANGES`. 

Por fim, atualizações `major` não apresentam necessariamente features ou correções mas que não tem `Backward compatibility`, isto é, apresentam `BREAKING CHANGES`, quebras na interface pública da aplicação, por exemplo, métodos que mudam de nome, pedem argumentos diferentes, passam a retornar respostas diferentes, e etc.

Os módulos e projetos declaram então em seus projetos `range selectors` para as versões dos seus pacotes, por exemplo `"react": "^18.0.0"` (Com `^` no início), representa que o módulo aceita a versão `18.0.0` do `React` mas também qualquer uma de suas atualizações `patch` ou `minor`, por outro lado,  `"react": "~18.0.0"` (Com `~` no início) representa que o módulo aceita a versão `18.0.0` do `React` mas também qualquer uma de suas atualizações `patch`, por fim, `"react": "18.0.0"` indica que o módulo aceita apenas a versão `18.0.0` do `React` e maneira exata, entretanto, esse comportamento só se observa quando o projeto não tem um `package-lock.json`.

Podemos checar as dependências desatualizadas com o comando:

```bash
npm outdated
```

Apesar do `npm` não ter uma ferramenta nativa de atualização interativa de dependências, podemos usar um outro pacote, o `npm-check-updates`, através do comando:

```bash
npm npm-check-updates -i
```

O que abrirá uma tela interativa para atualizar dependência a dependência do projeto, a recomendação é então começar pelas atualizações de `patch`, então `minor` e por fim `major`.

Ao atualizar as dependências é comum que surjam os chamados erros de `peer dependencies`, os **dependências em pares**, mas que poderiam ser traduzidas como **dependências compartilhadas**, essas dependências tem haver com a forma como o `npm` otimiza o download e gerenciamento dos `node modules`, evitando baixar várias vezes as dependências que são necessárias para vários módulos simultaneamente, isto é, se 3 das nossas dependências tem como dependência um mesmo módulo, digamos, o `React`, ao invés de baixar três vezes esse pacote, ao resolver a árvore de dependências o `npm` o instala apenas uma vez e compartilha essa instalação para todos os 3 pacotes que dependem dela, o problema é que ao atualizar uma dependência, o range de versões que ela aceita dessa sub dependência pode mudar sem que o `npm` perceba e faça o download de uma nova versão que esteja nesse range, por isso, temos o `ERESOLVE` ou `Error Resolve`, uma erro ao resolver a árvore de dependências, que normalmente pode ser solucionado instalando uma nova versão da sub dependência que esteja no range solicitado ou simplesmente apagando o `package-lock.json` e a pasta `node_modules` e rodando `npm install` para que o `npm` resolva as dependências do zero. 

Um outro problema pode surgir em dependências como o `eslint`, por vezes, ele passará por atualizações de `major`, porém, como em projetos completos o seu funcionamento depende de vários plugins como o `eslint-config-next` no momento do update talvez esses plugins ainda não tenham sido atualizados, o que gera problemas na implementação, nesses casos, a única solução é esperar que esses plugins sejam atualizados para só então fazer a atualização do módulo.

# Licenças 
Um outro tema discutido no Dia 33 foi o uso das Licenças, documentos que tem validade legal e que determinam como as pessoas podem usar, modificar e distribuir o seu software.

Isso é algo que, superficialmente, parece irrelevante, mas já foi fruto de muitos problemas para repositórios open source gigantescos, como o próprio `React`, que em 2017 resolveu trocar a sua licença atual, a ``MIT`` por uma outra, chamada `BSD` em conjunto com uma arquivo muito polêmico, chamado `Patents` que juntos determinavam que qualquer um que processasse o mantenedor do repositório, o Facebook, teria a liberdade para usar o `React`, `Jest` e outros projetos open source revogada, o que levou a um estado de FUB (Fear, Uncertainly and Doubt - Medo, Incerteza e Dúvida) na comunidade de software livre e sobretudo no mercado, com grandes empresas ameaçando deixar de utilizar o React e com grandes organizações repudiando a decisão do Facebook, como o `Apache Software Foundation` que colocou a licença na sua lista de licenças proibidas, proibindo todo e qualquer projeto financiado pela fundação de utilizá-la, sob a ameaça de perder o financiamento, o ápice da crise ocorreu quando o WordPress disse que deixaria de utilizar o React em detrimento dessa mudança, 8 dias depois, o time do React se pronunciou dizendo que voltaria atrás, adotando a licença MIT novamente.

Ao criar um projeto open source que terá grande impacto e alcance, é importante então escolher bem a licença, nesse caso, a disparadamente mais usada é a licença `MIT`, seguida pela `Apache2.0`, ambas, muito permissivas.

```
MIT License

Copyright (c) 2026 Yan Lima

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```