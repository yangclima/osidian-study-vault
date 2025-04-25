O tema principal abordado no dia 5 foi o versionamento de projetos utilizando [[Dia 2#Git *versus* GitHub|Git]] e como essa ferramente se tornou literalmente indispensável em ambientes de desenvolvimento profissionais.
# A história dos sistemas de versionamento
O problema de controlar as versões do nosso código está longe de ser algo atual, antes do sistemas de versionamento a unica maneira de trabalhar com algo pelo menos parecido era confiar no extremamente volátil `Ctrl + z` da sua IDE ou duplicar as pastas do seu projeto especificando a versão em cada uma delas, formando algo como um backup entre as features, porém, além da baixa eficiência de armazenamento, imagine o quão caótico seria trabalhar em equipe e sempre que for fazer o `merge`, a junção dos trabalhos feitos, precisar manualmente conferir em que arquivos você trabalhou e também manualmente resolver qualquer conflito que possa aparecer, pensando em resolver esse problema, em 1972 a *Bell Labs* criou o RCS o *Revision Control System*, que precedeu o CVS, e então o SVN. O grande problema é que esses sistemas funcionavam com um sistema de Check-in/Checkout, onde você "alugava" ou "reservava" um arquivo e durante aquele tempo, só você poderia alterá-lo, não parece algo tão complicado, porém muitas vezes os devs esqueciam de fazer o checkout, ou precisavam trabalhar no mesmo arquivo, o que era impossível nesse tipo de sistema (Sistemas Centralizados). Foi então que, em 2005, Linus Torvalds visando melhorias na forma em que os diversos colaboradores trabalhavam no desenvolvimento do Linux, criou o Git, o primeiro sistema de versionamento descentralizados, que como veremos permite que cada desenvolvedor tenha um cópia do diretório e a edite sem problemas na sua máquina pessoal.
# Como o Git funciona
Como vimos, o Git, sendo um sistema descentralizado, nos permite editar um versão local do repositório oficial em nossa máquina, assim sendo, pensando logicamente, poderia fazer sentido armazenar apenas as diferenças (`diff`) entre o repositório na nuvem e as alterações que forem feitas, isso é justamente que o Git  NÃO faz, na verdade alguns dos seus antecessores faziam isso, porém, a alta eficiência no armazenamento vinha com uma custo: Processos muito longos, sendo assim, o Git procurou um meio termo entre duplicar as pastas e armazenar apenas as diferenças, guardando então apenas os arquivos modificados em objetos que chamamos de *blob* (*Binary large object*), o que acontece então é: O blob inicial é idêntico a versão do repositório que você clonou do GitHub (Ou qualquer outro serviço de armazenamento de repositórios Git) e então sempre que você versiona o seu código ele cria um novo blob com todos os arquivos que foram alterados.
# Versionando com Git
O Git cria uma espécie de linha do tempo do seu repositório e essa é sua magia, podemos livremente viajar nessa linha do tempo sempre que for necessário, apesar de que vez ou outra surgirão efeitos colaterais, e isso nos permite consertar erros e trabalhar com muita confiança no desenvolvimento de novas features ou qualquer outra coisa sem nos preocupar em quebrar o nosso sistema, afinal, sempre poderemos voltar no tempo e consertar nosso erro. 

Pense nessa linha do tempo como tendo nós, que são os momentos que escolhemos guardar, e cada nó, seria então uma foto, mostrando o estado do nosso repositório num instante específico do tempo, e criando novos nós conseguimos expandir nossa linha temporal, o interessante é que cada desenvolvedor pode ter uma linha do tempo única no seu computador sem problema algum e depois juntar todas essa linha criando uma linha do tempo canônica no nosso repositório remoto.
## Clonando um repositório remoto
Como vimos, no nosso repositório remoto nós temos a linha do tempo principal, a linha do tempo oficial, assim digamos, então o primeiro passo do versionamento é esse, trazer para minha máquina o repositório que só existe na nuvem, como de costume, isso deve ser feito pelo terminal usando o comando:
```bash
git clone <linkDoRepositorioRemoto>
```
O comando acima clonará o seu repositório em uma pasta com o nome do repositório que está disponível na nuvem, porém podemos mudar isso:
```bash
git clone <linkDoRepositorioRemoto> <pastaDeDestino>
```
Ou apenas clonar na pasta atual:
```bash
git clone <linkDoRepositorioRemoto> .
```
## Os três estágios de um arquivo
No controle de versionamento Git, um arquivo pode esta em 3 estágios durante o nosso desenvolvimento:
1. **Untracked** ou **Modified**: O primeiro estágio de um arquivo com relação a nossa linha do tempo é Untracked, quando ele simplesmente não foi adicionado a nossa linha do tempo e não está sendo rastreado pelo Git ou Modified, quando ele foi modificado porém nós ainda não avisamos ao Git dessa mudança, nesse estado os arquivos estão fora do "foto".
2. **Staged**: O segundo estágio dos arquivos é Staged, quando nós já avisamos ao Git da sua adição ou modificação e é como se ele estivesse em cima de um palco, pronto para que nós tiremos a foto e ele apareça lá.
3. **Commited**: O terceiro e último estágio, é  quando justamente "tiramos a foto", criamos um novo nó e este arquivo está lá, aparecendo nessa foto no mesmo estado em que se encontra atualmente.
## Gerenciando o estado (Versionando)
É gerenciando o estado dos nossos arquivos que nós controlamos a versão do nosso software, versionamos, selecionando corretamente que arquivos entrarão em cada foto e qual o momento ideal para tirar a nossa foto, que momento é marcante para fazer isso, para essa tarefa os comandos principais são:  `status`, `log`, `add` e `commit`.
### `git status`
O Git status mostra o estado atual do seu repositório: Que arquivos e diretórios estão em cada estado (untracked, modified, staged), exceto aqueles que estão commited, pois esses já "estão na foto".
```bash
git status
```
### `git log`
O Git log, mostra o histórico do seu do seu repositório, seguindo nossa analogia, seria como exibir todas as fotos que já foram tiradas,  até agora, mesmo aquelas que não foi você quem tirou, mas que estavam presentes na linha do tempo original que você clonou, assim, seria algo como exibir a linha do tempo.
```bash
git log
```
#### Flags:
- `--stat`: Mostra uma forma menos resumida, exibindo que arquivos foram modificados e quais as mudanças.
- `--oneline`: Mostra uma forma mais reduzida, onde cada commit ("foto") é exibido em uma linha única.
### `git add`
O Git add é o comando responsável por alterar o estado dos arquivos ou diretórios de Untracked ou Modified para Staged, ou seja, enquadrá-los na foto, colocar-los no palco onde a foto sera tirada.
```bash
git add <nomeDoArquivo/Diretorio>
```
Se você quiser adicionar todas as modificações de uma vez, ou seja, mudar o estado de todos os arquivos de Untracked ou Modified para Staged numa só tacada você pode usar
```bash
git add .
```
### `git commit`
O Git commit é o comando responsável por de fato tirar a foto, mudando o estado de todos os arquivos Staged para Commited e adicionando essa foto, esse **COMMIT** ao histórico do seu repositório, mesmo que, por enquanto, só localmente.
```bash
git commit 
```
Ao rodar o commit acima, o git irá abrir um editor para que você escreva o texto que irá descrever o seu commit, para agilizar podemos declarar o comando da seguinte forma:
```bash
git commit -m <descricaoDoCommit>
```
#### Flags:
- `-m` (Message): Permite adicionar a descrição no próprio comando de commit, como visto acima.
- `--amend`: Emenda o commit anterior, ao invés de criar um novo commit ele excluirá o anterior e unirá as modificações dele com as novas do commit atual, já que commits são imutáveis.