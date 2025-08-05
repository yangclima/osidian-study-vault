Qualquer que seja a  [[Transformações lineares|Transformação linear]] $T: V \rightarrow W$, tal que $\dim{V} = n$ e $\dim{W} = m$ e sejam $\mathcal{A}$ e $\mathcal{B}$ bases para $V$ e $W$ respectivamente, existe uma matriz $[T]^{\mathcal{A}}_{\mathcal{B}}$ denominada **matriz de $T$ em relação as bases $\mathcal{A}$ e $\mathcal{B}$** tal que:
$$
[T(v)]_{\mathcal{B}} = [T]^{\mathcal{A}}_{\mathcal{B}} [v]_{\mathcal{A}} 
$$
Ou seja, aplicar a transformação linear $T$ a qualquer vetor de $V$ é equivalente a multiplicar esse vetor à esquerda pela matriz $[T]^{\mathcal{A}}_{\mathcal{B}}$, que por sua vez pode ser obtida da seguinte forma:
$$
[T]^{\mathcal{A}}_{\mathcal{B}} = [ \ [T(a_1)]_{\mathcal{B}} \ | \ \cdots \ \ | [T(a_2)]_{\mathcal{B}} \ ]
$$
Resumindo, cada coluna $j$ de $[T]^{\mathcal{A}}_{\mathcal{B}}$ é $[T(a_j)]_\mathcal{B}$, ou seja, o vetor imagem correspondente a aplicação de $T$ ao $j$-ésimo vetor da base $\mathcal{A}$ escrito com relação a base $\mathcal{B}$.

> Em geral, se a transformação ocorre de um espaço de dimensão $m$ para  um espaço de dimensão $n$ a Matriz de transformação linear correspondente tem ordem $m \times n$.

> Caso as bases $\mathcal{A}$ e $\mathcal{B}$  sejam as bases canônicas a matriz da transformação é chamada de **matriz canônica de $T$** e é denotada simplesmente por $[T]$







