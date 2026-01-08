Vimos que para permitir uma abordagem mais metódica e nos fornecer uma abstração conveniente, é útil e prática a definição de [[Variável Aleatória Contínua|variáveis aleatórias]] bem como uma [[Função massa de probabilidade]], assim, faremos a definição desses termos para a aplicação na [[Atualização Bayesiana]]:

- $\theta$ é a variável que representa o valor da hipótese
- $p(\theta)$ é a **função massa de probabilidade a priori** da hipótese
- $p(\theta|\mathcal D)$ é a **função massa de probabilidade a posteriori** da hipótese
- $p(\mathcal D | \theta)$ é a **função verossimilhança**, note sempre que essa, apesar da notação confundir, não é uma função probabilidade.

Assim, nossa tabela seria:

| $\theta$  | $p(\theta)$ | $p(\mathcal D\|\theta)$ | $p(\theta)p(\mathcal D\|\theta)$ | $p(\theta\|\mathcal D)$ |
| --------- | ----------- | ----------------------- | -------------------------------- | ----------------------- |
| $\cdots$  | $\cdots$    | $\cdots$                | $\cdots$                         | $\cdots$                |
| $\cdots$  | $\cdots$    | $\cdots$                | $\cdots$                         | $\cdots$                |
| **total** | $1$         | $-$                     | $p(\mathcal D)$                  | $1$                     |


