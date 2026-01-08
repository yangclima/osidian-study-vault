No objetivo de simular experimentos de probabilidade, A linguagem [[R]] possui algumas funções bem específicas:
```R
# A função 'sample' recebe como 1º arg um conjunto  'S' e como 2º um
# inteiro 'n' e então retorna uma permutação aleatória de n itens de
# 'S'
x <- c(1,2,3,4,5)
sample(x, 2)
# [1] 2 1
sample(x,2)
# [1] 3 5

# Também é possível permitir a repetição de elementos através do arg
# opcional 'replace', o que também remove a restrição n <= length(x)
y = sample(1:6, 12, replace=TRUE)
# [1] 1 4 5 2 1 4 4 3 1 6 2 1
```