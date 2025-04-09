# Operações
## Matemáticas
Em BSL as expressões matemáticas (Bem como qualquer chamada de função) são definidas no formato `(<primitive> <expression)` onde `<primitive>` são os operadores, e.g. `+`, `-`, `*`, `/`, `sqr`, `sqrt`...
```bsl
(+ 1 2 (* 2 3) (/ 1 2) (sqr 2) (sqrt 2))
; OUT: #i14.914213562373096
```
A saída dessa operação seria `#i14.914213562373096`, o `#i` indica que o número é um aproximação.
# Lógicas
A operações lógicas seguem o mesmo processo visto para as operações matemáticas, veja:
```bsl
; GREATER THAN
(> 100 10)
; OUT: true

; LESS THAN
(< 100 10)
; OUT: false

; GREATER THAN OR EQUAL TO
(>= 100 10)
; OUT: true

; LESS THAN OR EQUAL TO
(<= 100 10)
; OUT: false

; EQUAL TO
(= 100 10)
; OUT: false

; STRING EQUAL TO
(string=? "foo" "bar")
; OUT: false

; AND
(and (> 10 1) (< 1 10))
; OUT: true

; OR
(or (> 10 1) (< 1 10))
; OUT: true

; NOT
(not (> 10 1))
; OUT: false
```
# Constantes
Constantes são definidas no formato `(define <constant name> <constant value>)` e.g:
```bsl
(define PI 3.14)
(define RADIUS 3)

(define CIRCLE-AREA (* PI (sqr RADIUS)) )
```
# Comentários
Comentários são definidos da seguinte maneira
```bsl
; basic comment: a temp comment
;; documentation comment
```
# Strings
Strings em BSL são criadas sempre entre aspas duplas e podem ser operadas através de diversas funções:
```bsl
"Hello world!"

(string-append "Hello" " " "world!")
; OUT: "Hello world!"

(substring "Hello world!" 0 5)
; OUT: "Hello"

(string-length "hello")
; OUT: 5

```
# Imagens
A linguagem BSL tem suporte ao trabalho muito simples e possui para isso diversas funções que para esse objetivo obtidas através da importação de um módulo. Veja:
```bsl
;; Importa o módulo image da sugunda edição do livro how to design programs
(require 2htdp/image)

(circle <radius> <solid or outline> <color>)
(rectangle <width> <height> <solid or outline> <color>)
(square <side> <solid or outline> <color>)
(regular-polygon <size of side> <number of sides> <solid or outline> <color>)
(text <string> <size> <color>)
```
Além disso há funções que podem operar sobre as imagens criadas posicionando-as da forma que você quiser:
```bsl
(require 2htdp/image)

;; Dispõe 3 círculos um abaixo do outro
(above (circle 10 "solid" "red")
       (circle 20 "solid" "red")
       (circle 30 "solid" "red"))

;; Dispões 3 círculos um do lado do outro
(beside (circle 10 "solid" "red")
        (circle 20 "solid" "red")
        (circle 30 "solid" "red"))

;; Dispões 3 círculos um sobreposto ao outro
(overlay (circle 10 "solid" "red")
         (circle 20 "solid" "red")
         (circle 30 "solid" "red"))

;; Retorna o tamanho horizontal da imagem
(image-width (circle 10 "solid" "red"))
; OUT: 20

;; Retorna o tamanho vertical da imagem
(image-width (circle 10 "solid" "red"))
; OUT: 20
```
# Funções
Em BSL funções são definidas da seguinte maneira `(define (<function-name> <parameters>)<function-body>)` e.g.:
```bsl
(define (solid-circle color)
    (circle 40 "solid" color))
```
# Branching
Blocos `if` são definidos da mesma forma que as chamadas de função e as operações, no formato `(if <predicate> <case-true> <case-false>)`, note que predicado é uma expressão ou função que retorna um valor booleano, veja:
```bsl
(if (< 10 100) 
    "Is less!"
    "Not is less!")
; OUT: "Is less!"

(if (< 100 10) 
    "Is less!"
    "Is not less!")
; OUT: "Is not less!"

(cond [(< 100 10) "Is less!"]
      [(> 100 10) "Is greater!"]
      [else "Is equal!"])
```