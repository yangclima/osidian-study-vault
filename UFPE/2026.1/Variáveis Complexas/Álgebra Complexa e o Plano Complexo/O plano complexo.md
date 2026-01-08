Os [[Números Complexos]] são compostos por dois números reais  $x$ e $y$, dessa maneira, podemos, de forma conveniente, representar um número $z = x+yi$ como um vetor num plano onde o eixo horizontal, apelidado então de **eixo** real, representa a parte real de $z$ e o eixo vertical, chamado de **eixo imaginário** representa sua parte imaginária

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.2]
  % Eixos
  \draw[->] (-0.2,0) -- (3,0) node[right] {$\mathrm{Re}$};
  \draw[->] (0,-0.2) -- (0,3) node[above] {$\mathrm{Im}$};

  % Ponto z = a + bi (exemplo: a=2, b=1.5)
  \coordinate (Z) at (2,1.5);
  \fill (Z) circle (2pt) node[above right] {$z=x+yi$};

  % Projeções (linhas pontilhadas)
  \draw[dashed] (Z) -- (2,0) node[below] {$x$};
  \draw[dashed] (Z) -- (0,1.5) node[left] {$y$};

  % Vetor posição
  \draw[->] (0,0) -- (Z);
\end{tikzpicture}
\end{document}
```

Esse plano formado pelos eixos real e imaginário tem um gigante importância na matemática e é chamado de **plano complexo** e nos fornece uma visão geométrica dos números complexos como vetores no plano complexo e uma intuição melhor a respeito da [[Aritmética de números complexos]], vindo daí então, por exemplo, o motivo de falarmos em **magnitude de um número complexo**.

Além disso, como esses números se somam e se subtraem como vetores podemos aplicar aqui propriedades úteis da geometria como a **desigualdade triangular** e definir:

----

**Desigualdade triangular:** Sejam $z_1$ e $z_2$ dois números tais que $z_1,z_2\in \mathbb{C}$ então, vale que:
$$
|z_1| + |z_2| \geq |z_1 + z_2|
$$

---- 

Além disso, passamos a poder pensar em outras formas úteis de representar esses números, dentre as quais, a mais importante é, sem dúvida, a sua representação no sistema de coordenadas polares, isto é, podemos representar um número complexo através de um ângulo $\theta$ e um comprimento $r$.

```tikz
\begin{document}
\begin{tikzpicture}[scale=1.1]
  % Eixos
  \draw[->] (-0.2,0) -- (3,0) node[right] {$\mathrm{Re}$};
  \draw[->] (0,-0.2) -- (0,3) node[above] {$\mathrm{Im}$};

  % Ponto z = a + bi (exemplo)
  \coordinate (Z) at (2,1.5);
  \fill (Z) circle (2pt) node[above right] {$z=x+yi$};

  % Projeções
  \draw[dashed] (Z) -- (2,0) node[below] {$x$};
  \draw[dashed] (Z) -- (0,1.5) node[left] {$y$};

  % Vetor posição
  \draw[->, thick] (0,0) -- (Z) node[midway, above left] {$|z|$};

  % Arco do ângulo theta
  \draw (0.8,0) arc (0:36.87:0.8);
  \node at (1.05,0.25) {$\theta$};

  % (Opcional) marca no eixo real
  \fill (2,0) circle (1.5pt);
  \fill (0,1.5) circle (1.5pt);
\end{tikzpicture}
\end{document}
```


Note então que $r$ é igual a magnitude de $z$, e como podemos definir $x = |z|\cos{(\theta)}$ e $y = |z|\sin{(\theta)}$ então, $\theta = \arctan{\left(\dfrac{x}{y}\right)}$.

---- 

**Coordenadas Polares:** Um número complexo qualquer $z = x + yi$ pode ser representado no sistema de coordenadas polares através de um comprimento $r$ e um ângulo $\theta$ onde

$$
\begin{cases}
r = |z| \\
\theta = \arctan{\left(\dfrac{x}{y}\right)}
\end{cases}
$$

Da mesma forma, temos que $Re(z) = |z|\cos{(\theta)}$ e $Im(z) = |z|\sin{(\theta)}$.

----

O ângulo $\theta$ é também chamado de **argumento do número complexo** e denotado por $\theta = \text{arg}(z)$ .
