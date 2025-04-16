# for
```java
// for(variavel, condição, incremento)
for(int i = 0; i < 10; i++){
  // Repete 10 vezes esse bloco
}
```
# while 
```java
int i = 0;
while(i < 10){
  i++;
  // Repete 10 vezes esse bloco (enquanto a cond. for true)
}
```
# for-each (enhanced loops)
O for-each funciona objetos que são coleções (Que implementam o método iterable): 
```java
int[] numeros = {1, 2, 3, 4};

for (int n : numeros) {
    System.out.println(n);
}
```