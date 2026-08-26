No Brasil trabalhamos com dois padrões de tensão de fornecimento: $380/220\ V$ ($380$ trifásico e $220$ monofásico) ou $127/220\ V$ ($127$ trifásico e $220$ monofásico), onde aqui no Nordeste o primeiro padrão é o utilizado, além disso, o fornecimento pela concessionária pode se dar com $2$ (F+N), $3$ (2F+N) ou $4$ (3F+N) condutores e essa entrada é especificada de acordo com a carga da prevista em projeto, onde, nesse sentido, são importantes os seguintes conceitos:

1. **Potência Instalada** ($kVA$ ou $kW$): $100\%$ das cargas previstas em projeto considerando que todas estão em funcionamento.
2. **Demanda** ($kVA$ ou $kW$): Somente a parte da carga que está em funcionamento.

A medida que realizamos o projeto podemos ir realizando alguns passos que simplificarão no final das contas o processo de finalização desse projeto, o primeiro passo é então, verificar as informações iniciais do projeto:

1. Verificar o **Pé Direito**
2. Verificar **Espessura da Laje**
3. Verificar Peculiaridades do Projeto: a) Parte coberta e descoberta; b) Itens pouco claros do projeto; c) Unidade de Medida do projeto (Recomenda-se colocar sempre o projeto em Metros).

Outra coisa que nos ajuda muito na boa e rápida execução de um projeto são as configurações do AutoCAD, as principais são:

1. Nas opções (`OP` + `Enter`), indo na aba *User Preferences*, é recomendado desativar as duas checkbox de *Windows Standard Behavior*, a primeira desativa a edição de texto com duplo clique e a segunda habilita repetir a última ação ou finalizar a ação atual utilizando o botão direito do mouse.
2. Indo na aba *Display* e então clicando no botão  *Colors*, para melhorar a visualização do projeto podemos alterar o background do *Model* para *Black*.
3. Indo na aba *Open and Save* é recomendado configurar *Save as* como `Autocad 2018 Drawing (*.dwg)` para arquivos manter os arquivos mais leves e configurar, para uma maior segurança configurar  *Automatic Save* para um tempo menor, por exemplo, 5 minutos.

O último passo antes de, de fato começar o projeto é limpar a planta baixa, normalmente enviada pelo arquiteto, para que os itens do projeto elétrico fiquem em primeiro plano.

Para tal, removemos todas as informações que são irrelevantes para o projeto elétrico, tais como cotas de nível, fachadas, cortes transversal e longitudinal, diminuímos as legendas e juntamos tudo em uma camada só, executando o comando `PURGE` sempre e excluindo as camadas não utilizadas até que toda a planta fique numa única camada (`FAM ARQUITETURA`) a qual deixaremos com a cor `253` por ser um cinza claro que não chamará para si a atenção.

Unimos então toda a planta baixa em um bloco e criamos uma espécie de tabela conforme a seguinte imagem:

![[prje_001.png]]