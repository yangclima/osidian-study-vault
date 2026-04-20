O grande sucesso das [[Equações de Maxwell no domínio do tempo|equações de Maxwell]] deve-se, em parte, à predição da existência das ondas eletromagnéticas bem como a caracterização simples dos materiais através da **Condutividade** $\sigma$ (*Siemens por Metro*), **Permissividade** $\varepsilon$     (*Faraday por Metro*) e da **Permeabilidade** $\mu$ (*Henry por Metro*).

No vácuo, essas grandezas são $\sigma = 0 \ S\cdot m^{-1}$, $\mu = \mu_0 = 4\pi\times10^{-7} \ H\cdot m^{-1}$ e, por fim, $\varepsilon = \varepsilon_0 = 8.8542\times10^{12} \ F\cdot m^{-1}$.

Dessa forma, temos as relações constitutivas para os campos a, válidas na maioria dos materiais:

$$
\vec D = \varepsilon\vec E
$$

$$
\vec B = \mu\vec H
$$

$$
\vec J = \sigma \vec E
$$

Em contraste, a nano estrutura dos materiais pode ser complexa e muitas vezes requer ferramentas da mecânica quântica para ser entendida completamente. Felizmente as aproximações clássicas para átomos e moléculas são suficientes para entender a origem de $\varepsilon$, $\mu$ e $\sigma$.


# Condutividade 
A condutividade é um propriedade macroscópica da matéria que mede a sua capacidade de conduzir corrente elétrica, sendo representada pela letra grega $\sigma$ e sendo expressa na unidade *Siemens por Metro* $[S\cdot m^{-1}]$.

Nos **metais e semicondutores do tipo n** (materiais como Silício ou Germânio dopados com pequenas quantidades de átomos doadores que se ionizam facilmente nas temperaturas de operação, liberando elétrons livres), a condução elétrica ocorre principalmente pelo movimento desses elétrons livres. Esses elétrons podem percorrer distâncias equivalentes a muitos diâmetros atômicos antes de sofrer colisões com átomos da rede cristalina, impurezas ou outras partículas, eventos nos quais perdem momento. Quando um pequeno campo elétrico é aplicado ao condutor, ele exerce uma força sobre os elétrons livres e os acelera continuamente entre colisões. O equilíbrio entre a aceleração causada pelo campo elétrico e o espalhamento devido às colisões estabelece uma velocidade média de deriva dos elétrons, que resulta em uma corrente elétrica constante no material.

A densidade total de corrente $\vec J$ $[A\cdot m^{-2}]$ é proporcional a velocidade média dos elétrons $\langle \vec v \rangle$ $[m\cdot s^{-1}]$  e à densidade numérica de elétrons livres $n$ $[m^{-3}]$ (Os metais tem, tipicamente, 1 elétron livre por átomo e os semicondutores tem um elétron livre por átomo doador), além disso, por razões não óbvias ([[Modelo de Drude]]), a velocidade média dos elétrons é proporcional a $\vec E$ e portanto, sendo $-e$ a carga de um elétron:

$$
\vec J = -en\langle \vec v \rangle = \sigma \vec E
$$

Em líquidos o processo de condução é semelhante e os principais portadores de carga são os íons.

Em **semicondutores do tipo p** (materiais dopados com pequenas quantidades de átomos aceitadores com tendência a capturar elétrons como o Boro), os átomos de impureza adicionados capturam elétrons provenientes da banda de valência, tornando-se íons negativos. Esse processo deixa lacunas na banda de valência conhecidas como **buracos**. Como a energia térmica disponível é normalmente suficiente para que um elétron se mova de um átomo neutro vizinho para preencher a lacuna,  os buracos parecem se deslocar através do cristal.

Resumidamente, os semicondutores possuem uma banda de condução (Uma Família de possíveis estados de onda dos elétrons)  na qual elétrons livres podem se mover longas distâncias, separada de uma banda de valência onde os elétrons não podem se mover, e quando os elétrons são excitados da banda de valência para a de condução, tornam-se livres para se mover em resposta a um campo elétrico.

Correntes de fuga em materiais isolantes também tem processos de condução semelhantes e podem incluir fracas correntes superficiais além de condução em volume.

Em materiais exóticos, a condutividade pode depender da direção e pode ser representada por uma matriz $3\times 3$ denotada por $\overline{\overline{\sigma}}$.

Um último mecanismo de condução é a **Supercondutividade**, apresentada em alguns materiais sob condições muito específicas, neles, pares de elétrons conhecidos ficam fracamente ligados magneticamente numa conexão que envolve seus Spins e movem-se em unidades conhecidas como **Pares de Cooper**, a mecânica quântica impede que essa unidades interajam com a estrutura cristalina perdendo energia, porém, esses pares desprendem-se acima de uma temperatura crítica limite (Geralmente algo em torno de $77 \ K$) e também podem se desprender sob o efeito de um campo magnético suficientemente forte para alinhar os  seus Spins, dessa forma, a corrente elétrica nesses materiais fica limitada pela quantidade desses pares e pelo campo magnético gerado pela corrente que pode acabar separando-os.

Um último mecanismo de condução é a **supercondutividade**, observada em alguns materiais sob condições específicas de baixa temperatura. Nesses materiais, elétrons próximos ao nível de Fermi podem formar pares fracamente ligados conhecidos como **pares de Cooper**, resultantes de uma interação atrativa efetiva mediada pelas vibrações da rede cristalina. Esses pares possuem spins opostos e comportam-se como entidades quânticas coletivas que podem mover-se pelo cristal sem sofrer espalhamento dissipativo com a rede. A presença de um **gap de energia supercondutor** impede que pequenas excitações térmicas quebrem esses pares, permitindo que a corrente elétrica flua sem resistência. Entretanto, acima de uma **temperatura crítica** característica do material, ou na presença de um **campo magnético suficientemente forte**, os pares de Cooper são quebrados e o material retorna ao estado normal. Além disso, correntes muito intensas podem gerar campos magnéticos internos capazes de destruir o estado supercondutor, limitando assim a corrente máxima que pode ser transportada pelo material.