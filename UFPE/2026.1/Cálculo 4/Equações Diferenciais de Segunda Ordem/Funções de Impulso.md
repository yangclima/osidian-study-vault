Em algumas aplicações, em especial na engenharia, é necessário analisar fenômenos de comportamento impulsivo, como [[Potencial elétrico|tensões]] de grandes magnitudes aplicadas em períodos de tempo muito curtos.

Para trabalhar com problemas desse tipo, definimos uma **[[Função|função]] impulso unitário** designada por $\delta(t)$ para a qual valem as propriedades:

$$\delta(t) = 0; t\neq 0$$
$$\int_{-\infty}^{\infty}\delta(t)dt = 1$$

Nenhuma função comum satisfaz essas propriedades, por isso, $\delta$ é um exemplo das chamadas funções generalizadas, e é, em geral, chamada de **Delta de Dirac**.

Como $\delta(t)$ representa, um impulso unitário em $t=0$, em geral, $\delta(t-t_0)$ representa um pulso unitário em $t=t_0$.

Essa função é especialmente útil em [[Equações Diferenciais]] de sistemas mecânicos ou elétricos funcionando como excitação do sistema no caso em caso essa excitação tem caráter impulsivo, pode se provar, que essa função tem [[Transformada de Laplace]] dada por:

$$\mathcal{L}\{\delta(t-t_0)\} = e^{-st_0}$$