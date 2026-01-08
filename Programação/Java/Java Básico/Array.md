---
tags:
  - Java
---
Arrays são objetos java que armazenam sequências de um determinado tipo especificado, e. g. `String[] stringList = {"Hello", "world!"}`, ou seja, `TipoDeDado[] nomeDaVariavel = {el1, el2, ..., eln}` ou `TipoDeDado[] nomeDaVariavel = new TipoDeDado[tamanhoDoArray]`. O array tem tem tamanho fixo, podemos acessar seus elementos da seguinte forma:
```java
String[] test = {"a", "b", "c"};
String[] test1 = new String[100];

System.out.println(test[0]);
// Out: "a"
```
Para mudar um elemento executamos:
```java
String[] test = {"a", "b", "c"};

test[0] = "z";

System.out.println(test[0]);
// Out: "z"
```
# Arrays multidimensionais
Também é possível criar arrays multidimensionais para representar matrizes, veja:
```java
int[][] matriz = new int[3][3];

matriz[0][0] = 1;
```