O dia 25 teve como principal função gerar algumas alterações e refatorações no projeto, além de passar algumas discas valiosas sobre a postura que devemos adotar para se destacar no nosso ambiente de trabalho.
# `dotenv-expand`
As vezes é útil criar variáveis de ambiente que sejam dependentes de outras variáveis, por exemplo uma connection string nas variáveis de ambiente que seja construindo usando as properties de conexão também das variáveis de ambiente, isso é possível usando o módulo `dotenv-expand` que atua em conjunto com o [[Dia 18#Acessando variáveis de ambiente com `dotenv`|dotenv]] e permite coisas do tipo:
```shellscript
ENDPOINT=migrations
ROOT_URL=clonetabnews.yanlima.com

MIGRATIONS_URL=$ROOT_URL/$ENDPOINT
```
# Fazendo requests com `curl`
Além do que já vimos sobre o [[Dia 16#curl|curl]], é possível utilizá-lo para realizar requisições com diferentes métodos http, utilizando a flag `-x`, o commando ficaria então:
```bash
curl -x <method> <url>
```
# Gerenciando o aprendizado
O aprendizado pode ser buscado através de dois caminhos: o caminho automático e o caminho manual, o automático é aquele clássico exemplo do `Ctrl + C` `Ctrl + V` e te posiciona como apenas um proxy entre a inteligência buscada e o objetivo que ela vai te permitir alcançar, ou seja, você só repassa informações sem absorver nada dela, no caminho manual, entretanto, você se posiciona da mesma forma, porém a absorção do conhecimento envolvido permite que você adicione aquele conhecimento ao próprio banco de dados e a partir dali, o replique, alcançando a maior transferência possível, esse conhecimento citado pode ser embasado com base no princípio da [[Prática Direta]].
# Bottom line
Bottom line, que pode ser traduzido como lucro líquido é o resultado final de uma operação numa empresa, aquilo que sobra após uma serie de descontos e deduções, é essa linha que define o sucesso sob o ponto de vista da muralha de negócios, o profissional que tenta entender o que afeta essa linha e que se esforça e trabalha para aumentá-la, é quem verdadeiramente se destaca num ambiente de negócios, independente da área.