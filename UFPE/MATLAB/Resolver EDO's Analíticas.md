Para resolver [[Equações Diferenciais]] usando o MATLAB podemos fazer:

```MATLAB
syms y(t);

edo = diff(y,t,2) - 5*diff(y,t) + 6*y == 2*exp(t);

sol = dsolve(edo);

fprintf('SOLUÇÃO: %s \n', sol);
```

Onde `diff(y,t,n)` é a  $n$-ésima derivada de $y$ com relação a $t$. Ainda é possível resolver para condições iniciais usando:

```MATLAB
syms y(t);

edo = diff(y,t,2) - 5*diff(y,t) + 6*y == 2*exp(t);

cond1 = y(0) == 1;
Dy = diff(y, t);
cond2 = Dy(0) == 0;
conds = [cond1, cond2];

sol = dsolve(edo, conds);

fprintf('SOLUÇÃO: %s \n', sol);
```

