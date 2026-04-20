## Conceitos

### Número complexo

#### Explicação

Forma padrão $z=x+yi$, com $x$ parte real e $y$ parte imaginária.

#### Exemplo (se aplicável)

Se $z=3-4i$, então $
\Re(z)=3$ e $\Im(z)=-4$.

### Conjugado e módulo

#### Explicação

O conjugado troca o sinal da parte imaginária: $\overline{z}=x-yi$. O módulo mede a distância até a origem: $|z|=\sqrt{x^2+y^2}=\sqrt{z\overline{z}}$.

#### Exemplo (se aplicável)

Para $z=3-4i$, temos $\overline{z}=3+4i$ e $|z|=5$.

### Forma polar e exponencial

#### Explicação

Um complexo pode ser escrito como $z=r(\cos\theta+i\sin\theta)=re^{i\theta}$, com $r=|z|$ e $\theta=\arg(z)$.

#### Exemplo (se aplicável)

Se $z$ está no plano com raio $r$ e argumento $\theta$, a mesma informação aparece na forma polar ou exponencial.

### Fórmula de Euler

#### Explicação

Liga trigonometria e exponencial por $e^{i\theta}=\cos\theta+i\sin\theta$.

#### Exemplo (se aplicável)

É a ponte usada para transformar expressões trigonométricas em exponenciais.

### Função complexa

#### Explicação

Em geral, $f(z)=u(x,y)+iv(x,y)$, onde $u$ é a parte real e $v$ a parte imaginária.

#### Exemplo (se aplicável)

Uma função complexa pode ser estudada separando suas partes real e imaginária.

### Derivada complexa

#### Explicação

A derivada é definida por $f'(z_0)=\lim_{z\to z_0}\frac{f(z)-f(z_0)}{z-z_0}$.

#### Exemplo (se aplicável)

Quando esse limite existe, a função é diferenciável no sentido complexo.

### Equações de Cauchy-Riemann

#### Explicação

Se $f(z)=u(x,y)+iv(x,y)$, então a diferenciabilidade exige $u_x=v_y$ e $u_y=-v_x$. Em coordenadas polares, isso vira $u_r=\frac{1}{r}v_\theta$ e $v_r=-\frac{1}{r}u_\theta$.

#### Exemplo (se aplicável)

São o teste principal para verificar analiticidade.

### Função harmônica

#### Explicação

Uma função $\phi$ é harmônica quando satisfaz $\nabla^2\phi=\phi_{xx}+\phi_{yy}=0$.

#### Exemplo (se aplicável)

Frequentemente aparece como parte real ou imaginária de funções analíticas.

### Função exponencial complexa

#### Explicação

A forma geral é $e^z=e^x\cos y+ie^x\sin y$.

#### Exemplo (se aplicável)

Seu módulo é $|e^z|=e^x$ e ela é periódica em direção imaginária: $e^{z+2\pi i}=e^z$.

### Logaritmo complexo

#### Explicação

O logaritmo é multivalorado: $\ln z=\ln|z|+i\arg(z)$. O ramo principal é $\mathrm{Ln}(z)=\ln|z|+i\mathrm{Arg}(z)$, com $\mathrm{Arg}(z)\in(-\pi,\pi]$.

#### Exemplo (se aplicável)

O valor de $\arg(z)$ muda em múltiplos de $2\pi$.

### Funções trigonométricas complexas

#### Explicação

Podem ser definidas por exponenciais: $\cos z=\frac{e^{iz}+e^{-iz}}{2}$ e $\sin z=\frac{e^{iz}-e^{-iz}}{2i}$.

#### Exemplo (se aplicável)

Essas definições preservam identidades parecidas com as do caso real.

### Transformações lineares complexas

#### Explicação

A forma geral é $f(z)=az+b$, com $a,b\in\mathbb{C}$.

#### Exemplo (se aplicável)

Dependendo de $a$, a transformação pode representar translação, rotação ou dilatação.

### Função recíproca

#### Explicação

A função $f(z)=\frac{1}{z}$ inverte o módulo e troca o sinal do argumento: $\frac{1}{z}=\frac{1}{r}e^{-i\theta}$.

#### Exemplo (se aplicável)

É útil para interpretar inversões no plano complexo.

### Limite e continuidade

#### Explicação

O limite $\lim_{z\to z_0}f(z)=L$ exige que a função se aproxime do mesmo valor por qualquer direção. Continuidade significa $\lim_{z\to z_0}f(z)=f(z_0)$.

#### Exemplo (se aplicável)

Se o valor depende do caminho, o limite não existe.

## Métodos

### Converter entre formas de representação

#### Explicação

Usar $z=x+yi$, $z=r(\cos\theta+i\sin\theta)$ e $z=re^{i\theta}$ como descrições equivalentes do mesmo número.

#### Quando usar

Ao multiplicar, dividir, elevar potências, extrair raízes ou interpretar geometricamente.

#### Relação com outros conceitos (se houver)

Depende de módulo, argumento e fórmula de Euler.

### Usar o módulo para comparar e estimar

#### Explicação

O módulo traduz o complexo em distância no plano.

#### Quando usar

Em desigualdades, limites e controle de erro.

#### Relação com outros conceitos (se houver)

Aplica-se junto com conjugado, produto e divisão.

### Aplicar a forma polar em produtos e quocientes

#### Explicação

Na forma polar, multiplicar soma ângulos e multiplica módulos; dividir subtrai ângulos e divide módulos.

#### Quando usar

Quando a conta algébrica fica pesada ou há potência/rotação envolvida.

#### Relação com outros conceitos (se houver)

É a leitura geométrica da exponencial complexa.

### Usar De Moivre para potências

#### Explicação

$\big(\cos\theta+i\sin\theta\big)^n=\cos(n\theta)+i\sin(n\theta)$.

#### Quando usar

Ao calcular potências de complexos em forma polar.

#### Relação com outros conceitos (se houver)

Vem diretamente da forma exponencial.

### Extrair raízes com a fórmula geral

#### Explicação

As $n$ raízes vêm dos ângulos $\frac{\theta+2k\pi}{n}$.

#### Quando usar

Ao resolver $z^n=w$ ou listar todas as raízes de um complexo.

#### Relação com outros conceitos (se houver)

Depende da forma polar e da periodicidade do argumento.

### Verificar diferenciabilidade por Cauchy-Riemann

#### Explicação

Calcular as derivadas parciais de $u$ e $v$ e testar se satisfazem as equações de Cauchy-Riemann.

#### Quando usar

Para decidir se uma função é analítica em um ponto ou região.

#### Relação com outros conceitos (se houver)

Conecta derivada complexa, funções harmônicas e analiticidade.

### Reescrever funções via exponenciais

#### Explicação

Senos e cossenos complexos podem ser reduzidos a exponenciais.

#### Quando usar

Em simplificações algébricas, identidades e manipulação de expressões complexas.

#### Relação com outros conceitos (se houver)

Conecta trigonometria, exponencial e Euler.

### Analisar transformações por parâmetros geométricos

#### Explicação

$f(z)=az+b$ separa deslocamento, rotação e escala.

#### Quando usar

Ao interpretar imagens de retas, círculos e regiões no plano complexo.

#### Relação com outros conceitos (se houver)

Depende da leitura polar de $a$.

### Testar continuidade por componentes

#### Explicação

O limite de $f(z)=u+iv$ existe quando as partes real e imaginária convergem separadamente.

#### Quando usar

Em problemas de limite e continuidade de funções complexas.

#### Relação com outros conceitos (se houver)

Reduz o problema complexo a dois limites reais.

## Procedimentos

### Identificar o tipo de número complexo

#### Passo a passo claro

1. Escreva o número na forma $x+yi$.
2. Separe parte real e imaginária.
3. Calcule o conjugado, se necessário, trocando o sinal de $i$.
4. Calcule o módulo por $|z|=\sqrt{x^2+y^2}$.

#### Resultado esperado

Representação algébrica pronta para operações.

#### Dica prática (se aplicável)

Use o conjugado para racionalizar divisões.

### Resolver multiplicação e divisão de complexos

#### Passo a passo claro

1. Em forma algébrica, distribua os termos e use $i^2=-1$.
2. Em forma polar, multiplique os módulos e some os argumentos.
3. Na divisão, divida os módulos e subtraia os argumentos.

#### Resultado esperado

Forma final simplificada do complexo.

#### Dica prática (se aplicável)

Prefira polar quando houver potências ou quocientes.

### Encontrar potências e raízes

#### Passo a passo claro

1. Transforme o número para a forma polar.
2. Para potências, aplique $z^n=r^n(\cos(n\theta)+i\sin(n\theta))$.
3. Para raízes, use $\theta_k=\frac{\theta+2k\pi}{n}$, com $k=0,1,\ldots,n-1$.

#### Resultado esperado

Todas as potências ou todas as raízes do número.

#### Dica prática (se aplicável)

Não esqueça dos múltiplos de $2\pi$ ao listar raízes.

### Verificar se uma função é analítica

#### Passo a passo claro

1. Escreva $f(z)=u(x,y)+iv(x,y)$.
2. Calcule $u_x$, $u_y$, $v_x$ e $v_y$.
3. Verifique se $u_x=v_y$ e $u_y=-v_x$.
4. Se estiver em coordenadas polares, use a versão polar das equações.

#### Resultado esperado

Decisão sobre diferenciabilidade e analiticidade.

#### Dica prática (se aplicável)

Se as equações falharem, a função não é analítica no ponto.

### Calcular derivada complexa por Cauchy-Riemann

#### Passo a passo claro

1. Encontre as partes real e imaginária da função.
2. Confirme as equações de Cauchy-Riemann.
3. Use $f'(z)=u_x+iv_x$ ou $f'(z)=v_y-iu_y$.

#### Resultado esperado

Derivada complexa da função.

#### Dica prática (se aplicável)

Escolha a forma mais simples conforme as derivadas já calculadas.

### Resolver limites e continuidade

#### Passo a passo claro

1. Reescreva a função como $u(x,y)+iv(x,y)$.
2. Verifique separadamente os limites de $u$ e $v$.
3. Compare o limite com o valor da função no ponto, se a questão for de continuidade.

#### Resultado esperado

Conclusão sobre existência do limite e continuidade.

#### Dica prática (se aplicável)

Se diferentes caminhos geram resultados diferentes, o limite não existe.

### Analisar transformações lineares

#### Passo a passo claro

1. Identifique $a$ e $b$ em $f(z)=az+b$.
2. Veja o efeito de $b$ como translação.
3. Escreva $a$ em forma polar para identificar rotação e escala.

#### Resultado esperado

Interpretação geométrica da transformação.

#### Dica prática (se aplicável)

Se $|a|=1$, há rotação pura; se $a>0$ real, há dilatação.
