---
tags:
  - Definição
---
Uma das principais aplicações das derivadas, usada nos mais diversos campos da ciência é a capacidade analítica provida por ele com relação às [[Função|funções]], através da [[Derivada]] podemos inferir diversos aspectos do [[O gráfico da função|gráfico de uma função]] e consequentemente estimar propriedades que nos interessem nesses gráficos. 

## Crescimento e Decrescimento
A primeira propriedade que podemos inferir através da [[Derivada]] é o crescimento/decrescimento da função num dado intervalo, podemos pensar da seguinte forma: Se, como vimos, a derivada representa o coeficiente angular da reta tangente e da mesma maneira representa a tendência imediata da função (A variação instantânea), então, se ela for positiva a função está crescendo e caso o contrário, a função está decrescendo, temos portanto as propriedades:
- Se $f^\prime(x) > 0$ num uma dado intervalo $I$ e $a, b \in I$, seja $a > b$, então $f(a) > f(b)$ e portanto a função pode ser dita **crescente**. 
- Se $f^\prime(x) < 0$ num dado intervalo $I$ e $a, b \in I$, seja $a < b$, então $f(a) > f(b)$ e portanto a função pode ser dita **decrescente**. 

## Máximos e Mínimos
Esse é um dos pontos mais importantes com relação a aplicação das derivadas e do cálculo em geral, já que é ele que nos permite realizar [[Otimização|otimizações]], ou seja, procurar valores máximos e mínimos de uma função. Pensando logicamente e usando a definição do tópico anterior que, sendo a função contínua e derivável no intervalo que nos interessa, para que $f^\prime(x) < 0$ assuma uma valor $> 0$ precisa passar por um valor de $x$ para o qual, $f^\prime(x) = 0$, esses, são chamados de pontos críticos e despertam nosso interesse, perceba que o mesmo ocorre para que uma função $f^\prime(x) > 0$  assuma um valor $< 0$, e consequentemente, nesses pontos a função que era crescente passa a ser decrescente (e vice-versa), formando assim, um pico (Ou vale, caso o contrário ocorra), temos portanto que:
- Se $f^\prime(a) = 0$ e $f^\prime(x) > 0$ para todo $x$ num intervalo $]b, a]$ onde $b < a$ e $f^\prime(x) < 0$ para todo $x$ num intervalo $[a, c[$ onde $c > a$, então $a$ é um máximo local de $f$
- Se $f^\prime(a) = 0$ e $f^\prime(x) < 0$ para todo $x$ num intervalo $]b, a]$ onde $b < a$ e $f^\prime(x) > 0$ para todo $x$ num intervalo $[a, c[$ onde $c > a$, então $a$ é um mínimo local de $f$

![[Pasted image 20250313165808.png| center]] 
