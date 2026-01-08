Para criar vetores, listas de elementos, em [[R]], utilizamos a seguinte sintaxe:
```R
# Criar uma lista com os elementos 1,2 e 3
x <- c(1,2,3)

# Criar uma lista com os elem. de 0 a 100
x <- 1:100

# É possivel fazer operações com vetores, o que equivale a
# realizar a operação em questão com cada elemento
x <- c(1,2,3)
y <- x + 2
# [1] 3,4,5


# Também é possível operar vetores de mesmo tamanho:
x = c(1,2,3)
y = c(2,3,4)
z = x * y
# [1] 2, 6, 12

# Além disso, podemos aplicar funções sobre vetores:
x = c(1,2,3)
y = sin(x)
# [1] 0.8414710 0.9092974 0.1411200
y = exp(x)
# [1]  2.718282  7.389056 20.085537


#Acessando elementos de um vetor
x <- c(1,2,3,4,5)

x[1]
# [1] 1

x[c(1,2,5)]
# [1] 1 2 5

x[2:5]
# [1] 2 3 4 5
