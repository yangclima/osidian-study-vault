---
tags:
  - Java
---
Uma String é um tipo não primitivo de dados que armazena uma sequência de caracteres e possui diversos métodos que podemos utilizar para trabalhar com essa sequência, é importante mensurar que a String é um [[Mutabilidade e Imutabilidade|tipo mutável]] e consequentemente não podemos alterar dinamicamente os valores armazenados em seus índices.
# Métodos
## `charAt`

```java
String test = "Hello world!";

// charAt(int index) -> char  
// Retorna o caractere armazenado no índice <index> da String  
System.out.println(test.charAt(1));  
// Out: 'e'
```
## `codePointAt`

```java
String test = "Hello world!";

// codeAtPoint(int index) -> int  
// Retorna o código unicode do  caractere armazenado no índice  
// <index> da String  
System.out.println(test.codePointAt(1));  
// Out: 101 (i.e. O código unicode referente ao char 'e')
```
## `compareTo`

```java
String test = "a";
String test1 = "c";

// compareTo(String otherString) --> int  
// Retorna o valor da comparação léxico-gráfica  
// da instância da String com outra string <otherString>  
System.out.println(test.compareTo(test1));  
// Out: -2
```
## `compareToIgnoreCase`

```java
String test = "a";
String test1 = "C";

// compareTo(String otherString) --> int  
// Retorna o valor da comparação léxico-gráfica  
// da instância da String com outra string <otherString>
// ignoramdo a diferença entre maiúsculas e minúsculas
System.out.println(test.compareTo(test1));  
// Out: -2
```
## `concat`

```java
String test = "abc";  
String test1 = "cb";  
  
// contains(CharSequence s) --> boolean  
// Retorna verdadeiro caso a instância atual de String  
// contenha a sequência de caracteres <s>  
System.out.println(test.contains(test1));  
// Out: false
```
## `contains`

```java
String test = "a";
String test1 = "C";

// compareTo(String otherString) --> int  
// Retorna o valor da comparação léxico-gráfica  
// da instância da String com outra string <otherString>
// ignoramdo a diferença entre maiúsculas e minúsculas
System.out.println(test.compareTo(test1));  
// Out: -2
```
## `contentEquals`

```java
String test = "abc";  
String test1 = "cba";  
  
// contentEquals(CharSequence cs) --> boolean  
// Retorna verdadeiro caso a instância atual de String possua  
// os mesmos caracteres, na mesma ordem, que a sequência de  
// caracteres <cs>  
System.out.println(test.contentEquals(test1));  
// Out: false
```
## `split`

```java
String test = "a b c";  
  
// split(String regex) --> String[]  
// Quebra a string em todos os índices que encontra  
// uma correspondência para a expressão Regex descrita na  
// string <regex> e retorna um array contendo as partes nas  
// quais a string foi subdividida  
System.out.println(Arrays.toString(test.split(" ")));  
// Out: [a, b, c]
```
## `indexOf`

```java
String test = "a b c";  
  
// indexOf(String str) --> int  
// Retorna o primeiro índice na String atual  
// em que aparece a substring <str> ou −1 caso  
// ela não apareça  
System.out.println(test.indexOf("b"));  
// Out: 2
```
## `isEmpty`

```java
String test = "";

// isEmpty() --> boolean  
// Retorna true caso a string não possua caracteres
// e false caso contrário
System.out.println(test.compareTo(test1));  
// Out: true
```
## `static join`

```java
String test = "a b c";  
  
// String.join(  
//      CharSequence delimiter, 
//      CharSequence... elements  
//      ) --> int  
// Retorna uma string formada pela junção de cada // elemento de uma sequência de caracteres <elements>  
// separados por um <delimiter>  
System.out.println(String.join("-", test.split(" ")));  
// Out: a-b-c
```
## `lastIndexOf`

```java
String test = "a b c b";  
  
// indexOf(String str) --> int  
// Retorna o último índice na String atual  
// em que aparece a substring <str> ou −1 caso  
// ela não apareça  
System.out.println(test.lastIndexOf("b"));  
// Out: 6
```
## `length`

```java
String test = "abc";

// length() --> int  
// Retorna a quantidade de  caraacteres, ou seja, o tamanho da 
// instância atual de String
System.out.println(test.length());  
// Out: 3
```
