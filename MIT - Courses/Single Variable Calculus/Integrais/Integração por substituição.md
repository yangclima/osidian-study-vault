A integração por substituição é um método de resolução de [[Integral Indefinida|Integrais]] que consiste, basicamente, na reversão do processo de derivação através da [[Métodos de resolução de derivadas#Derivada de função composta|regra da cadeia]] e utiliza bastante da notação dos [[Diferenciais]] por envolver uma troca de variável. A Integração por substituição pode ser aplicada sempre que o integrando for composto na forma $[f(g(x)\cdot g^\prime(x))]$ a menos de um fator constante e através desse processo transformamos uma função complicada em algo que conhecemos, veja o exemplo:
$$
\int x^3(x^4 + 2)^5 \ dx 
$$
Primeiro precisamos  reconhecer que temos em mãos um integrando que possui a característica acima, depois, identificamos que elemento da função seria o $g(x)$ e o apelidamos por uma variável (Normalmente $u$), nesse caso, tomaremos $u = x^4 + 2$:
$$
\int x^3(x^4 + 2)^5 \ dx  = \int u^5x^3 \ dx
$$
Para efetuar a derivação precisamos agora substituir o diferencial e o que sobrou da variável antiga ($x^3dx$) pelo diferencial $du$, sabendo que $du = 4x^3dx$ (Derivando $g(x)$) podemos inferir que $x^3dx = \frac{du}{4}$:
$$
\int u^5x^3 \ dx = \int \frac{1}{4} \cdot u^5 \ du 
$$
Agora já é possível resolver a integral com as integrais básicas que já conhecemos:
$$
\int \frac{1}{4} \cdot u^5 \ du  = \frac{1}{4} \cdot \int u^5 \ du = \frac{1}{4} \cdot \frac{u^6}{6} = \frac{u^6}{24}
$$
Por fim, temos que trazer de volta a variável original do integrando, substituir $u$ pelo seu valor em termos de $x$:
$$
\frac{u^6}{24} = \frac{(x^4 + 2))^6}{24}
$$
