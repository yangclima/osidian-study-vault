O código Gray foi pensado para resolver um problema relacionado a utilização do [[Sistemas de numeração digital|Sistema de numeração binário]] em [[Sistemas Digitais]] de alta velocidade, já que na passagem de um binário para o seu sucessor, algumas vezes, vários bits mudam de uma só vez, o que pode gerar erros na interpretação do seu valor se este for aferido enquanto os bits ainda estão mudando, dessa forma, o **Código Grey** foi pensado para que dois números consecutivos tenham apenas um bit de diferença.

A conversão de binário para Gray ocorre conforme a seguinte imagem:

![[sd_001.png]]

Ou seja, tomamos o dígito mais significativo do código Gray sempre igual ao do binário e os próximos valores são obtidos comparando os bits da sequência, se forem diferentes, o dígito será $1$, caso contrário, $0$.

A conversão de Gray para Binário é parecida e ocorre conforme a seguinte imagem:

![[sd_002.png|center]]

A grande diferença aqui é que comparamos o último dígito binário obtido com o próximo dígito Gray.

