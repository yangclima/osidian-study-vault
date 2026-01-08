Os testes de convergência que estudamos até aqui (O [[Teste da integral]] e os [[Testes de Comparação]]) funcionam somente para [[Séries]] com termos positivos, vamos então elaborar agora métodos para lidar com séries com termos não necessariamente positivos, em especial as chamadas **Séries alternadas**, séries que advém de [[Sequências]] cujos termos são alternadamente positivos e negativos. 

Seja a série alternada

$$
\sum_{n=1}^\infty (-1)^{n-1}b_n = b_1 - b_2 + b_3 - b_4 + \cdots
$$

Se essa série satisfaz:

1. $b_{n+1} \leq b_n$ (A sequência $|b_n|$ é decrescente)
2. $\lim\limits_{n\to\infty} b_n = 0$  (A sequência $b_n$ converge para $0$)

Então $\sum_{n=1}^\infty (-1)^{n-1}b_n$ é convergente.
