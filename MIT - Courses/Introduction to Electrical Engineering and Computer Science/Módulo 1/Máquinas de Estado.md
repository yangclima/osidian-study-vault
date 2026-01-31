Uma **máquina de estados** (_State Machine_) é um [[Abstração e Modularidade|modelo de abstração]] utilizado para descrever sistemas cujo comportamento **não depende apenas do input atual**, mas também de informações relevantes sobre o passado. Essas informações passadas **não são armazenadas explicitamente**, mas sim **condensadas em uma variável interna chamada estado**, que resume tudo o que o sistema precisa “lembrar” para determinar sua evolução futura.

A ideia central é que, em qualquer instante, o **estado atual contém toda a informação necessária do histórico de inputs** para prever tanto a saída produzida quanto o próximo estado do sistema. Assim: dado o estado atual e o input presente, o futuro independe do passado mais distante.

Máquinas de estados são tradicionalmente formuladas em **tempo discreto**, sendo amplamente utilizadas em computação, automação, controle lógico e modelagem de protocolos. Em contextos mais gerais de modelagem de sistemas físicos, essa noção pode ser estendida para sistemas de estado contínuo, descritos por [[Equações Diferenciais]], embora nesses casos o termo “máquina de estados” costume ser substituído por **modelo em espaço de estados**.

Formalmente, uma máquina de estados discreta é caracterizada pelos seguintes elementos fundamentais:

1. Um conjunto de estados possíveis $S$
2. Um conjunto de inputs admissíveis $I$, denominado **vocabulário de entrada**
3. Um conjunto de outputs possíveis $O$, denominado **vocabulário de saída**
4. Uma função de saída $o : I \times S \rightarrow O$, que associa a cada par (input atual, estado atual) um output
5. Uma função de transição de estados $n : I \times S \rightarrow S$, que determina o próximo estado do sistema
6. Um estado inicial $s_0 \in S$, que define a condição inicial da máquina

A cada passo de tempo, a máquina recebe um input, produz um output e atualiza seu estado interno de acordo com essas funções. Essa estrutura simples permite modelar sistemas complexos de forma rigorosa, previsível e modular, sendo uma das bases formais tanto da computação quanto da engenharia de controle e automação.