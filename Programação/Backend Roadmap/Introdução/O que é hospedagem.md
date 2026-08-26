# Fonte 01
> https://developer.mozilla.org/en-US/docs/Learn_web_development/Getting_started/Environment_setup/Browsing_the_web

Existem alguns termos em específico da área de desenvolvimento que causam certa confusão e muitas vezes são usados de modo errado, para evitar essa confusão, definiremos em detalhes cada uma:

1. Uma `Web Page`, às vezes chamada apenas de `Page` é um documento que pode ser exibido no navegador (Um software que encontra e exibe páginas à demanda), escrito na linguagem `HTML` e sendo acessado via um ``URL``, podendo ainda ser complementado por informações de estilo, scripts de comportamento e mídias.
2. Um `Website` é um conjunto de Web pages agrupados em um único recurso e conectadas por links, todas no mesmo [[O que é Domain Name|domínio]]
3. Um `Web Server` é um computador que hospeda um `Website` na internet
4. Um `Web Service` é um software que responde requisições pela internet para executar funções ou fornecer dados, geralmente é suportado por um `Web Server` e, como pode fornecer páginas para que o usuário acesse, alguns ``Websites`` são também ``Web Servers``, enquanto aqueles com conteúdo estático não o são.
5. Uma `Search Engine` é um `Web Service`, normalmente acessado pelo navegador, que te ajuda a encontrar outras páginas na web

Usando uma analogia, numa biblioteca:

> A biblioteca me si é um `Web Server`, as diferentes seções e estantes são como `Websites`, cada livro é uma `Webpage` e o índice de livros é como uma `Search Engine`

Algumas dicas para realizar pesquisas:

1. Usar `"<phrase>"` entre aspas indica para o mecanismo de busca que você quer sugestões com aquelas palavras e exatamente naquela ordem
2. Usar `-<word>` restringe à resultados que não contém `<word>`
3. Usar `<word1> OR <word2>` restringe a resultados que contém apenas uma das duas palavras
4. Usar `intitle:<word>` restringe a resultados onde `<word>` aparece no título da página principal

# Fonte 2:
> https://developer.mozilla.org/en-US/docs/Learn_web_development/Howto/Web_mechanics/What_is_a_web_server

O termo `Web Server` se refere simultaneamente a `Software` e `Hardware`

1. Pensando em hardware, o Web Server é uma máquina que armazena o software do server e os componentes de um Website, como arquivos HTML, JS, CSS...  se conectando a internet e suportando troca física de dados com outros dispositivos na web
2. Quanto a parte de software, um Web Server inclui várias partes que controlam como os dados são dispostos e como o usuário os acessa, sendo, no mínimo, um servidor [[O que é HTTP|HTTP]], que entende URL's e é acessado através do nome de domínio do website/webservice que hospeda sendo responsável por entregar o seu conteúdo para o usuário final

Um servidor como descrito pode ser ainda considerado estático ou dinâmico. No primeiro caso ele se responsabiliza apenas em entregar para o usuário o conteúdo que já existe nos seus diretórios, no segundo caso, ele tem ainda a capacidade de alterar ou complementar o conteúdo dos arquivos antes de entregá-los aos  usuários.

Tecnicamente é possível usar seu computador como um servidor web, porém, há uma grandiosa lista de motivos do porque é muito melhor hospedar num servidor dedicado, motivos como o seu tempo de disponibilidade e possuir endereço IP fixo.



