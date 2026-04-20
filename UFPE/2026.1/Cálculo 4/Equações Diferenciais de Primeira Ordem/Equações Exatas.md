Quando nos deparamos com uma equação tal como

$$2x + y^2 + 2xyy^\prime = 0$$

Que não é [[EDO's Lineares de Primeira Ordem|Linear]] e nem [[Equações Separáveis|Separável]], ficamos de mãos atadas com os métodos que desenvolvemos até agora, não podemos utilizar nem o [[Método dos Fatores Integrantes]] e nem o método de [[Separação de variáveis]], porém, para uma classe especial de funções na qual esse exemplo se encaixa, chamadas de **Equações Exatas** podemos desenvolver um novo método.

**Equações exatas** são [[Equações Diferenciais]] que escritas na forma diferencial padrão:

$$Mdx + Ndy = 0$$

Satisfazem a condição de que $M_y$ (A [[Derivadas parciais|Derivada parcial]] de $M$ com relação $y$) e $N_x$ (A [[Derivadas parciais|Derivada parcial]] de $N$ com relação $x$)  são iguais, isto é $M_y = N_x$.

Para esse tipo de equação, existe uma função $\psi(x,y)$ tal que $\psi_x = M$ e $\psi_y = N$ e podemos então substituir $M$ e $N$ na equação original:

$$\psi_xdx + \psi_ydy = 0$$

Assim, notamos que a EDO pode ser resolvida integrando ambos os termos em função das respectivas variáveis, obtendo então, como solução:

$$\psi(x,y) = c$$

