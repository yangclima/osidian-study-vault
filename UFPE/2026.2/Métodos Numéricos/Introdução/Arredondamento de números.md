Quando representamos um número $x$ com uma quantidade de dígitos menor que a quantidade de [[Dígitos Significativos]] estamos fazendo uma aproximação desse número. Chamamos esse processo de **arredondamento**.

Dado um número da forma:

$$x = \pm 0,d_1d_2\cdots d_t\cdots d_n \times 10^e$$

Podemos representar $x$ com $t$ dígitos usando:

- **Arredondamento por truncamento:** Aproximamos $x$ por $$\bar x = \pm 0,d_1d_2\cdots d_t \times 10^e$$ Simplesmente descartando os dígitos após o $d_t$.
- **Arredondamento por proximidade:** Se $d_{t+1}<5$Aproximamos $x$ por $$\bar x =  \pm 0,d_1d_2\cdots d_t \times 10^e$$ caso contrário, aproximamos $x$ por $$\bar x = \pm 0,d_1d_2\cdots (d_t+1) \times 10^e$$
- **Arredondamento por proximidade com desempate par:** Se $d_{t+1}<5$, aproximamos $x$ por $$\bar x = \pm 0,d_1d_2\cdots d_t \times 10^e$$ Se $d_{t+1}d_{t+2}\cdots > 5$ arredondamos $x$ para $$\bar x = \pm 0,d_1d_2\cdots (d_t+ 1) \times 10^e$$ Senão, no caso de empate, se $d_t$ for par aproximamos $x$ por $$\bar x = \pm 0,d_1d_2\cdots d_t\times 10^e$$ E caso $d_t$ seja ímpar: $$\bar x = \pm 0,d_1d_2\cdots (d_t+1)\times 10^e$$