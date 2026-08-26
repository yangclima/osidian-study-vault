A análise de malha é um método análogo a [[Análise Nodal]], mas, ao invés de usar as equações de [[Lei de Kirchhoff das Correntes|LKC]], utiliza as equações da [[Lei de Kirchhoff das Tensões]], uma para cada malha, ou seja, cada laço do seu circuito que não possui nenhum outro laço interno a ele.

Assim, atribuímos a cada malha uma **Corrente de Malha**, uma corrente que percorre toda aquela malha, mas que não necessariamente é a corrente que passa num elemento dessa malha, por exemplo, se um resistor está entre duas malhas, a corrente real que passa por ele pode ser escrita como a soma das correntes de cada uma das malhas. 

Assim, a aplicação da Análise de malha pode ser dividida em algumas etapas:

1. Primeiro, identificamos e nomeamos cada uma das malhas do circuito, uma dica é acima da identificação da malha (e.g. $a$, $b$, $c$, $\cdots$) desenhar uma seta no sentido que você percorrerá a malha, aqui, tomamos, por conveniência e devido a nossa [[Convenção de Variáveis Associadas]], como padrão o sentido horário para percorrer as malhas, aqui, devemos tomar um cuidado, como não sabemos facilmente qual a tensão ao longo de uma fonte de corrente é complicado lidar com esses elementos, mas podemos utilizá-los para escrever algumas equações de malha, afinal, como se trata de um [[Componentes Ideais|componente ideal]] ele reflete exatamente a corrente em um ramo, assim, se uma fonte de corrente $I$ está exclusivamente numa malha $a$ e a favor do sentido horário sabemos que sua corrente de malha é $I_a = I$, caso esteja no sentido anti-horário teremos $I_a = -I$, já se ela estiver entre duas malhas $a$ e $b$, teremos que, se ela estiver no sentido da corrente de $I_a$, $I_a - I_b = I$ ou, se ela estiver no sentido de $I_b$, teremos $I_b - I_a = I$, a partir daí, depois de escrever a equação que cada uma dessas fontes nos dá, as substituímos por curto circuitos, e encontramos as malhas nesse novo circuito, nesse caso, as malhas que não existiam antes e passaram a existir nesse novo circuito são chamadas de **Super Malhas**, pulamos esse passo se não tivermos fontes de corrente no nosso circuito.
2. O segundo passo é, para cada malha do circuito, escrever a sua equação de **LKT**, tomando, despreocupadamente, por base que você está entrando no nó positivo, isto é, todos os resistores terão tensão positiva, nessa etapa, ignoramos as fontes de tensão, então se circulamos uma malha $a$, de corrente de malha $I_a$, um resistor $R_1$ que pertence apenas a essa malha será mensurado na equação por um termo $I_aR_1$, já se um resistor $R_2$ estiver entre duas malhas $a$ e $b$, sua contribuição para a equação da malha $a$ é $(I_a - I_b)R_2$
3. O terceiro passo é somar no lado direito das equações de **LKT** obtidas, as contribuições das fontes de tensão de cada malha, nesse caso, as fontes que estão aumentando a tensão na direção da corrente de uma determinada malha são tomadas como positivas e as que estão diminuindo são tomadas como negativas.
4. Por fim, utilizamos  tudo o que obtemos para escrever o nosso [[Sistemas lineares|sistema linear]] e encontrar as correntes de malha e, a partir delas, qualquer parâmetro desejado do nosso circuito.

Quando o nosso circuito tem apenas fontes de tensão, é muito simples resolvê-lo, podemos fazer isso por inspeção, construindo um sistema linear matricial da forma:

$$[R][I]=[V]$$

Aqui, a matriz $[I]$ é a nossa matriz de incógnitas, dada por $[I] = [i_1| i_2| \cdots |i_n]$, com $i_n$ sendo a corrente de malha da $n$-ésima malha, podemos escrever então as outras duas seguindo:

1. O elemento $r_{ii}$, da diagonal da matriz $[R]$ é igual a resistência total dos resistores da $i$-ésima malha
2. O elemento $r_{ij}$ da matriz $[R]$ é igual ao negativo da soma das resistências conectadas entre a $i$-ésima e a $j$-ésima malha
3. O elemento $v_i$ é igual a soma das fontes de tensão conectadas na malha $i$ tomadas com um sinal positivo quando estão na mesma direção que a corrente de malha e com um sinal negativo quando estão na direção oposta

E então resolvemos utilizando algum método como a regra de Kramer ou a eliminação gaussiana.