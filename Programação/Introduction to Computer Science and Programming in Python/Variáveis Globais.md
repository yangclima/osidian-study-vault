Vimos que existe algo chamado [[Funções|escopo de função]] que cria novos  *naming spaces*  e que faz com que variáveis criadas dentro de funções não "existam" fora destas, porém, o contrário não é verdadeiro, variáveis criadas fora de funções, ou seja, dentro do *naming space*, ou mais propriamente do escopo do [[Módulos Python|módulo]] são acessíveis em qualquer parte do código e são chamadas de **Variáveis Globais**. Estas também podem ser definidas em outras partes do código, por exemplo no escopo de outras funções, caso sejam precedidas pela palavra-chave `global`.
```python
def f(x):
    global global_var
    global_var = 0
```
Apesar da utilidade, o uso desleixado de variáveis globais pode tornar  o nosso código muito complexo e destruir o que os cientistas da computação chamam de localidade.