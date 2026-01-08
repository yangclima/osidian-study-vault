O `matplotlib` é uma biblioteca do Python muito útil para a criação de gráficos para a visualização de dados, podemos importar de dentro da biblioteca o recurso `pyplot` que permite a criação de gráficos de uma forma sequencial, mais simples:

## Gráfico de linhas

```python
from matplotlib import pyplot as plt

eixo_x = ["01-10", "02-10", "03-10", "04-10", "05-10", "06-10", "07-10"]
eixo_y = [56, 94, 183, 122, 113, 245, 200]

plt.plot(eixo_x, eixo_y, color="green", marker="o", linestyle="None")

plt.title("Tempo de estudo por dia")
plt.ylabel("Tempo de estudo (Minutos)")
plt.xlabel("Dia do mês (2025)")

plt.show()
```

## Gráficos de barra
Os gráficos de barra são bons quando queremos mostrar como algumas quantidades variam em um conjunto particular de itens:

```python
from matplotlib import pyplot as plt

eixo_x = ["01-10", "02-10", "03-10", "04-10", "05-10", "06-10", "07-10"]
eixo_y = [56, 94, 183, 122, 113, 245, 200]

plt.bar(eixo_x, eixo_y)

plt.title("Tempo de estudo por dia")
plt.ylabel("Tempo de estudo (Minutos)")
plt.xlabel("Dia do mês (2025)")

plt.show()
```

![[dsdz_002.png|center]]

Além disso, pode também ser útil para criar histogramas (Apesar de existir uma função `hist` mais apropriada) para analisar a distribuição de valores.

```python
from matplotlib import pyplot as plt
from collections import Counter

grades = [83,95,91,87,70,0,85,82,100,67,73,77,0]

decile = lambda nota: (nota // 10)*10

histogram_x = [i for i in range(0, 101, 10)]


decile_count = Counter([decile(grade) for grade in grades])
histogram_y = [decile_count.get(i, 0) for i in histogram_x]
bar_width = 10


plt.bar(histogram_x, histogram_y, bar_width, edgecolor='black')

# Define a escala do eixo x
plt.xticks([10*i for i in range(11)])

plt.title("Distribuição de notas")
plt.xlabel("Decil")
plt.ylabel("# de alunos")

# Eixo x de -5 a 105 e Eixo y de 0 a 5
plt.axis([-5, 105, 0, 5])

plt.show()
```

![[dsdz_001.png|center]]

Perceba que aqui usamos um eixo `X` que vai de $-5$ a $105$ , utilizar eixos, seja o x ou o y, iniciando em valores que não sejam o x é uma feature que deve ser usada com muito cuidado já que  pode, muitas vezes fazer com que o gráfico gere impressões erradas.

# Gráfico de linhas
Como já vimos, podemos criar gráficos de linha com `plt.plot`, eles são ótimos para demonstrar tendências:

```python
from matplotlib import pyplot as plt

meses = ["Jan", "Fev", "Mar", "Abr", "Mai", "Jun", "Jul"]

planta_A = [0, 5, 10, 16, 22, 24, 25]
planta_B = [0, 8, 12, 16, 19, 20, 21]
planta_C = [0, 6, 11, 17, 20, 23, 24]

plt.plot(meses, planta_A, "g-", label="planta A")
plt.plot(meses, planta_B, "r-.", label="planta B")
plt.plot(meses, planta_C, "b:", label="planta C")

# Cria altomaticamente uma tabela de legenda
# loc=0 equivale ao canto superior esquerdo
plt.legend(loc=0)

# Escala do eixo y
plt.yticks(range(0, 31, 5))

plt.title("Crescimento Mensal das Plantas (Jan–Jul)")
plt.xlabel("Mês")
plt.ylabel("Altura (cm)")

plt.show()
```

![[dsdz_003.png|center]]

# Gráficos de dispersão
Um gráfico de dispersão é ótimo para demonstrar a relação entre duas variáveis correlacionadas, para criar gráficos desse tipo usamos a função `plt.scatter`:

```python
from matplotlib import pyplot as plt

nota_test2 = [ 99, 90, 85, 97, 80]
nota_test1 = [100, 85, 60, 90, 70]
label = ["a", "b", "c", "d", "e"]

plt.scatter(nota_test1, nota_test2)

for nota1, nota2, label in zip(nota_test1, nota_test2, label):
    plt.annotate(label, (nota1, nota2), xytext=(5,-5), textcoords='offset points')

plt.xlabel("Nota no teste 1")
plt.ylabel("Nota no teste 2")
plt.title("Nota no teste 1 Vs. Nota no teste 2")

plt.axis("equal")

plt.show()
```

![[dsdz_00.png|center]]

Perceba que adicionamos a linha `plt.axis("equal")`, isso garante que as escalas dos eixos sejam iguais e evita problemas de visualização.