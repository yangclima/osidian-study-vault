---
next: "[[Baterias]]"
---
O objetivo da ciência é fornecer uma compreensão dos fenômenos naturais a partir de cuidadosos resultados experimentais , apesar disso, para que, de fato esse conhecimento seja útil e aplicável na vida real, isto é, fora do ambiente controlado do laboratório, é essencial que sejam construídas uma série de abstrações entre os dados experimentais e as pessoas que querem manipular os fenômenos para atingir os seus objetivos, para que estes possa fazê-lo sem se preocupar com os detalhes minuciosos do experimento.

Essas abstrações são construídas com objetivos específicos em mente e se aplicam sob circunstancias bem definidas, ou seja, quando as restrições apropriadas são atendidas, e as primeiras dessas abstrações são, ainda no domínio científico, as **Leis da Ciência** que operam como definições concisas ou equações que permitem avaliar e prever [[Aspectos qualitativos e quantitativos dos materiais|qualitativa e quantitativamente]] um fenômeno específico sem se preocupar com o experimento em si.

A partir disso, pensando na engenharia como **o uso com propósito da ciência** e então a engenharia elétrica como o **uso com propósito das [[Equações de Maxwell]] para os fenômenos eletromagnéticos**, as abstrações são as ferramentas essenciais para lidar com os fenômenos cotidianos da área sem ter que retornar sempre aos detalhes complexos e dispendiosos da física experimental.

Imagine um circuito simples, uma lâmpada conectada com uma bateria e pense o quão complicado seria se, sempre que nos deparássemos com esses circuitos precisássemos fazer complexos e dispendiosos cálculos nos preocupando com cada detalhes específico da lâmpada, com as reações químicas internas da bateria, e ainda outros detalhes, enquanto um circuito simples como esse já é uma tarefa ultra complexa, a análise de circuitos mais complexos seria impossível, então como poderíamos facilitar esse processo?

A resposta está na **Abstração de circuitos de parâmetros agrupados**, que se baseia na chamada **Disciplina de discretização**, também chamada de *lumping*, a ideia é pegar características físicas que estão distribuídas no espaço e concentrá-la em um único ponto ou componente idealizado e realizar com eles cálculos se atendo apenas a valores específicos e relevantes e não mais com as características internas de cada dispositivos elétrico.

Por exemplo, no caso do nosso circuito da lâmpada e da bateria, podemos substituir a lâmpada por um elemento discreto, nesse caso, um resistor, cuja única grandeza física relevante é a [[Resistência]] e substituir a bateria por um fonte ideal de tensão, cuja única característica física relevante é a [[UFPE/2025.2/Física 3/Eletrostática/Potencial elétrico|tensão nominal]], então, poderíamos prever o comportamento do circuito através da simples relação

$$
I = \dfrac{V}{R}
$$

Essa é a ideia geral da abstração de circuitos, modelamos complexos mecanismos físicos através de elementos discretos os quais possuem terminais com os quais podemos interagir, como na seguinte imagem:

```tikz
\usepackage{circuitikz}
\begin{document}
\begin{circuitikz} 
\ctikzset{bipoles/generic/width=1.5, bipoles/generic/height=0.8}
    \draw[scale=2]
    % Representação do Elemento Discreto (Lumped Element)
    (0,0) 
    to[short, o-] (1,0) 
    to[generic, l=Elemento] (3,0) 
    to[short, -o] (4,0);
\end{circuitikz}
\end{document}
```

Esses elementos são modelados de tal forma que a única maneira de interagir com eles é através de [[Corrente]] e tensão nos seus terminais.

Quantos as restrições para aplicação dessa abstração temos o seguinte:

1. A variação temporal do [[Fluxo magnético]] por qualquer caminho fechado fora dos elementos deve ser zero, isto é: $$\dfrac{\partial\Phi_B}{\partial t} = 0 $$
2. Não há acúmulo ou variação de [[Carga]] dentro dos elementos ao longo do tempo, ou seja: $$\dfrac{\partial Q}{\partial t} = 0 $$
3. O circuito deve operar num regime tal que a escala temporal dos sinais de interesse são muito menores que o atraso de propagação das [[Ondas Eletromagnéticas Planas|ondas eletromagnéticas]] através dos elementos, o que pode ser pensado como "o comprimento de onda ($\lambda$) das ondas eletromagnéticas deve ser **muito maior que as dimensões físicas do circuito**".

São essas abstrações que vão garantir o funcionamento e aplicabilidade das leis que possibilitam a análise de circuitos. ]

O nosso próximo passo agora é entender o funcionamento dos principais componentes reais dos circuitos para conseguir modelar o seu funcionamento através dos componentes ideais através da abstração que estamos construindo.
