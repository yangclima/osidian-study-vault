Como vimos, nem todos os números reais podem ser representados como [[Números de Ponto Flutuante]], por conta disso, muitas das operações realizadas por um computador tem uma imprecisão associada, tanto por truncamento, para números muito grandes, muito pequenos, irracionais ou dízimas quanto em cálculos realizados entre números. 

O conjunto $F$ não é fechado para as operações numéricas, de modo que o resultado de uma operação aritmética entre dois números que pertencem a $F$ pode não ter representação exata nesse conjunto e por isso não devemos esperar que as operações aritméticas sejam realizadas de maneira exata num computador digital, assim sendo, costumamos representar as operações de soma, subtração, multiplicação e divisão na **aritmética de ponto flutuante** como $\oplus$, $\ominus$, $\otimes$ e $\oslash$, respectivamente.

É natural de se imaginar que a [[Arredondamento de números|aproximação]] de qualquer número de ponto flutuante $x\notin F$ por um número de ponto flutuante $fl(x)\in F$ deveria ser o mais próximo possível de $x$ dentro daquele conjunto, isto é, ser o menos distante possível desse número que pode ser representado em $F$, ou seja:

$$|x - fl(x)| \leq |x-f| \ \ \forall f\in F $$

Onde $fl(x): \mathbb{R} \mapsto F$. Ademais, dada uma base $\beta$ do sistema de ponto flutuante, sabe-se que todo número real $x$ localizado na abrangência de $F$ (Dentro do intervalo dos limites de representação definidos pela base e a gama de expoentes) pode ser representado por um elemento de $F$ com erro relativo não maior que:

$$u = \frac{1}{2}\beta^{1-t}$$

Assim, supondo $\beta^L < x < \beta^U$, temos que:

$$\frac{|fl(x) - x|}{|x|} \leq \frac{1}{2}\beta^{1-t}$$

Chamamos $u$ de **unidade de arredondamento** e temos que, se $x$ fica na abrangência de $F$, então:

$$fl(x) = x(1 + \delta), \ \ \ |\delta|< u$$

Assim, cada operação na aritmética de ponto flutuante tem um erro de no máximo $u$, denominado erro unitário de arredondamento.

> Uma última definição é o chamado **Epsilon da máquina** ($\epsilon$), definido como o menor número que adicionado a $1$ resulta em um número diferente de $1$, isto é, $fl(x+\epsilon) > 1$ de modo que descreve a precisão dos cálculos de ponto flutuante, além disso $\epsilon = 2u$.

Para checar o valor do epsilon de máquina no seu computador pessoal você pode usar o seguinte comando no [[MATLAB]]:

```
eps
```

Ou pela definição:

```MATLAB
e = 1;
i = 1;
 
while 1+e > 1
    e = e/2;
end

disp(e);
```

Podemos também ver o menor número representável na máquina usando `realmin` e o maior representável usando `realmax`.

Normalmente, quando usamos números de precisão simples, há 23 bits alocados para a mantissa, porém, há também um bit implícito (Uma sacada do padrão IEEE 754), logo, temos $24$ bits para a mantissa, nesse caso, $\epsilon = 2^{1-24} = 2^{-23} \approx 1,1912\times 10^{-7}$ garantindo uma precisão de cerca de $6$ casas decimais, por outro lado, usando números de precisão dupla, temos $52$ bits explícitos e $1$ implícito, logo $\epsilon = 2^{1-53}= 2^{52} = 2,2204\times 10^{-16}$ garantindo cerca de $15$ casas de precisão.