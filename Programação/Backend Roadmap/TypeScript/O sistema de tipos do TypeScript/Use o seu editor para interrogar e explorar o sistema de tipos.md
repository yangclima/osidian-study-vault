Quando instalamos o TypeScript baixamos com ele o `tsc`, o nosso compilador e o `tsserver` um servidor TS independente responsável pelo autocomplete e outras funcionalidades, englobadas no que chamamos de Language Services, não temos muito contato com esse servidor, a maioria de nossa interação com ele se dá através da nossa IDE, que será nossa grande aliada no desenvolvimento e nos ajudará a fazer uso das principais vantagens do TS.

As principais features, presentes na maioria das IDE's modernas, são:

1. Podemos passar o cursor por cima da declaração de uma variável para ver o tipo inferido para ela pelo TS
2. Podemos passar o cursor por cima da declaração de uma função para ver o tipo inferido para os seus argumentos e retorno
3. Podemos passar o cursor por cima das citações a uma variável, ótimo para ver como a tipagem evolui ao longo de partições das estruturas condicionais
4. Podemos passar o cursor acima de um método em uma cadeia de métodos para entender como o TS infere os tipos com base na sequência de métodos
5. Podemos posicionar o cursor sobre um erro de tipos indicado na IDE para entendê-lo e algumas vezes ter algum insight de como resolvê-lo
6. Em algumas IDE's (Funciona no VS Code, use F2) você pode renomear os atributos de um tipo automaticamente, isso é diferente de "Localizar e Substituir", a IDE sabe renomear somente o atributo que você tem interesse, sem renomear atributos de outros objetos mesmo que o atributo deles tenha o mesmo nome
7. Mesmo que os tipos pertençam a bibliotecas externas você consegue usar `Go To Definition` para ver a declaração do tipos e objetos entendendo melhor sua natureza e utilização, familiarize-se com isso.

Em conclusão, a sua IDE é uma poderosa aliada ao codar TypeScript, familiarize-se com ela e suas funcionalidades e aproveite seu potencial,