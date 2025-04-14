---
tags:
  - Java
---
O Java é uma linguagem fortemente tipada, o que significa  que na declaração de variáveis (Assim como na definição parâmetros) nós precisamos definir o tipo de dado que a variável criada armazenará. Os tipos de dados, por sua vez, são divididos em dois tipos, os tipos primitivos e não primitivos, o primeiro tipo se refere a valores em si, o segundo, à objetos, que possuem atributos, métodos e etc.
# Tipos primitivos
## byte
```java
byte n = 0;
```
`byte` é um tipo primitivo de dado que armazena um inteiro de 8 bits, onde 7 bits representam seu valor numérico e 1 bit representa o seu sinal (Positivo ou negativo) tendo assim seu valor limitado a números entre -128 e 127. 
## short
```java
short n = 0;
```
`short` é um tipo primitivo de dado que armazena um inteiro de 16 bits, onde 15 bits representam seu valor numérico e 1 bit representa seu sinal,  tendo assim seu valor limitado a números entre -32,768 e 32,767.
## int
```java
int n = 0;
```
`int` é um tipo primitivo de dado que armazena um inteiro de 32 bits, onde 31 bits representam seu valor numérico e 1 bit representa seu sinal,  tendo assim seu valor limitado a números entre -2,147,483,648 e 2,147,483,647.
## Long
```java
Long n = 0L;
```
`long` é um tipo primitivo de dado que armazena um inteiro de 64 bits, onde 63 bits representam seu valor numérico e 1 bit representa seu sinal,  tendo assim seu valor limitado a números entre $-2^{63}$ e $2^{63}-1$.
## float
```java
float n = 0.0f;
```
`float` é um tipo de dado primitivo que armazena um [[Números de Ponto Flutuante|número de ponto flutuante]] de 32 bits conforme o padrão IEEE 754. Por conta da forma na qual sua definição e armazenamento ocorrem, o ponto flutuante suporta valores numéricos muito mais altos, porém, possui uma grande imprecisão em suas operações e representações.
## double
```java
double n = 0.0d;
```
`double` segue os padrões da IEEE 754, armazenando um [[Números de Ponto Flutuante|número de ponto flutuante]] de 64 bits e possuindo a mesma vantagem e limitação que o tipo `float`.
## boolean
```java
boolean n = false; 
```
`boolean` é um tipo primitivo de dado capaz de armazenar apenas o valor `true` ou `false` sendo utilizado largamente para sinalizadores simples que indicam condições do tipo verdadeira/falsa.
## char
```java
char n = '\u0000';
```
`char` é um tipo primitivo que armazena um caractere unicode qualquer de 16 bits, variando de '\u0000' até '\uffff'.
## Literais
Os valores atribuídos aos valores primitivos podem ser definidos na inicialização da variável ou por meio do sinal de atribuição (` = `) utilizando os literais, valores explicitamente definidos no código fonte sem que seja necessário realizar cálculos.
### Literais de inteiros
Existem dois tipos de literais inteiros, o literal `int` e o literal `long`, sua distinção é feita através de uma peculiaridade do literal `long` que deve ser criado sempre utilizando-se `L` (Ou `l`) no final. Os literais `int` podem ser atribuídos a  qualquer variável dos tipos `byte`, `short` ou `int` ou `long`, entretanto valores que excedem o limite numérico dos inteiros devem ser representados como literais `long` e atribuídos apenas a variáveis do tipo `long`. 
```java
int u = 123456;
byte v = 126;
Long w = 123456789L;
```
Os literais inteiros podem ser representados através de 3 sistemas numéricos: decimal, hexadecimal e binário. Veja:
```java
// 27 em decimal
int dec = 27

// 27 em hexadecimal
int hex = 0x1b

// 27 em binário
int bin = 0b11011
```
### Literais de ponto flutuante
Os literais de ponto flutuante são do tipo `float` caso contenham `f` ou `F` no final e do tipo `double` caso o contrário,  podendo ou não conter `d` ou `D` no final.
```java
float u = 123.456f
double v = 123.456
```
Eles também podem ser representados usando a notação científica por meio da letra `e` ou `E`.
```java
float u = 1.23456e2f
```
### Literais de char
Os literais `char` devem sempre ser declarados com aspas simples e devem conter ou o caractere a ser armazenado explicitamente (Caso o seu sistema de arquivos e sua IDE permita) ou seu caractere de escape unicode e. g. `'\u0108'`.  Os java também possui caractere de escapes próprios, são eles:
- `\b` (backspace), 
- `\t` (tab), 
- `\n` (line feed), 
- `\f` (form feed), 
- `\r` (carriage return), `
- \"` (double quote), 
- `\'` (single quote), 
- `\\` (backslash).
