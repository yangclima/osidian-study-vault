---
tags:
  - Java
---
# If-then-else
```java 
if (cond1) {
  // Se cond1 for verdadeira, executa esse bloco
} else if (cond2) {
  // Se cond2 for verdadeira, executa esse bloco
} else {
  // Se cond1 e cond2 forem falsas, executa esse bloco
}
```
# switch case
```java
switch (variable) {
  case value: {
    // Se variable == value executa esse bloco
    break;
  }
  case value1: {
    // Se variable == value1 executa esse bloco
    break;
  }
  default {
    // Se variable não corresponder a nenhum case acima;
    // executa esse bloco
  }
}
```
É importante usar o `break`, o java não consegue interpretar os blocos corretamente e caso ache um `case` verdadeiro e não encontre um break, executará todos os blocos abaixo.
# Operador ternário
```java
// cond ? <cond true> : <cond false>
boolean isAdult = age ? true : false; 
```