---
tags:
  - Java
---
O java Scanner é a forma mais comum de coletar inputs dos usuários, ele está disponível na lib `java.util.Scanner` e deve ser usado da seguinte forma:

```java
import java.util.Scanner;

Scanner scanner = new Scanner(System.in);

// Colete os dados

scanner.close();
```

A coleta dos dados por der feita da seguinte forma

```java
System.out.println("Insira seu nome!");
String input1 = scanner.nextLine(); // coleta uma string vinda do input
int input2 = scanner.nextInt(); // coleta um int vindo do usuário
```