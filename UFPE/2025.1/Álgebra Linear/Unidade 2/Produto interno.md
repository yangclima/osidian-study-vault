Um produto interno definido num [[Espaços vetoriais|espaço vetorial]] $V$ é um regra que faz cada par de vetores $(u,v)$ corresponder a um número real $\langle u,v \rangle$, satisfazendo:
1. Bilinearidade: $\langle \lambda u + \lambda^\prime u^\prime, v \rangle = \lambda\langle  u, v \rangle + \lambda^\prime\langle u^\prime, v\rangle$ e $\langle u, \lambda v + \lambda^\prime v^\prime \rangle = \lambda\langle  u, v \rangle + \lambda^\prime\langle u, v^\prime\rangle$
2. Simetria: $\langle u, v\rangle = \langle v, u\rangle$
3. Positividade definida: $u \neq 0 \implies \langle u, u \rangle \geq 0$ 

Utilizando-se do produto interno é possível definir conceitos como ângulo, comprimento (Norma) e ortogonalidade, em qualquer espaço $n$-dimensional. Um espaço vetorial munido de um produto interno definido é denominado **espaço vetorial Euclidiano** que define:
1. Norma: $||u|| = \sqrt{\langle u, u\rangle}$
2. Distância: $dist(u,v) = ||u - v||$ 
3. Ortogonalidade: $u \perp v \implies \langle u, v \rangle = 0$
4. Ângulo: $\cos{\theta} = \dfrac{\langle u, v \rangle}{||u||||v||}$ 

Além disso, valem as propriedades:
1. Desigualdade de Cauchy-Schwartz: $|\langle u,v \rangle| \leq ||u||||v||$
2. Desigualdade triangular: $||u + v|| \leq ||u|| + ||v||$
