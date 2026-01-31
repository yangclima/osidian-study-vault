Enquanto as interações das [[Carga|cargas]] com os campos [[Campo Elétrico|elétricos]] e [[Campo Magnético|magnéticos]] são caracterizadas pela [[Lei da força de Lorentz]], as [[Equações de Maxwell]] caracterizam a origem desses campos bem como a interação entre eles.

A forma mais comum de enunciar essas equações é a forma diferencial onde utilizamos para isso o operador *Del* ($\nabla$), dado por:

$$
\nabla = \frac{\partial}{\partial x}\hat x + \frac{\partial}{\partial y}\hat y + \frac{\partial}{\partial z}\hat z
$$

Onde $\hat x$, $\hat y$ e $\hat z$ são os versores do espaço tridimensional cartesiano. É importante também lembrar do conceito de [[Divergente]] $\nabla \cdot \vec A$  e do conceito de [[Rotacional]] $\nabla \times \vec A$.

Assim, as equações de Maxwell podem ser enunciadas como:

$$
\begin{equation}
\nabla \cdot \vec D = \rho
\tag{Lei de Gauss Elétrica}
\end{equation}
$$

$$
\begin{equation}
\nabla \cdot \vec B = 0
\tag{Lei de Gauss Magnética}
\end{equation}
$$
$$
\begin{equation}
\nabla \times \vec E = - \frac{\partial \vec B}{\partial t}
\tag{Lei de Faraday}
\end{equation}
$$
$$
\begin{equation}
\nabla \times \vec H = \vec J +  \frac{\partial \vec D}{\partial t}
\tag{Lei de Ampère-Maxwell}
\end{equation}
$$

E as variáveis envolvidas são:

1. $\vec E$ (*Campo elétrico*)
2. $\vec H$ (*Campo Magnético*)
3. $\vec B$ (*Densidade de [[Fluxo magnético]]*)
4. $\vec D$ (*Deslocamento Elétrico*)
5. $\vec J$ (*Densidade de [[Corrente]]*)
6. $\rho$ (*Densidade de [[Carga]] elétrica*)

Algumas dessas grandezas são introduzidas para descrever o comportamento dos campos eletromagnéticos na presença de meios materiais. No caso particular do **vácuo**, as relações constitutivas assumem a forma simples
$$\vec B = \mu_0 \vec H, \ \ \ \vec D = \varepsilon_0 \vec E$$
Onde $\varepsilon_0 = 8.8542\times 10^{-12} \ F\cdot m^{-1}$ é a **Permissividade elétrica do vácuo** e $\mu_0 = 4\pi \times 10^{-7} H\cdot m^{-1}$ é a **Permeabilidade magnética do vácuo**. 

Em **meios materiais condutores simples**, a densidade de corrente elétrica pode ser modelada pela [[Modelo de Drude|Lei de Ohm Microscópica]], nesse caso:

$$
\vec J = \rho \vec v = \sigma \vec E
$$

onde $\sigma$ é a condutividade elétrica do meio. Essa relação constitui uma hipótese constitutiva adicional sobre o material e não decorre diretamente das equações de Maxwell.

Para o vácuo temos então:

$$
\begin{equation}
\nabla \cdot \vec E = \frac \rho \varepsilon_0
\tag{Lei de Gauss Elétrica}
\end{equation}
$$

$$
\begin{equation}
\nabla \cdot \vec B = 0
\tag{Lei de Gauss Magnética}
\end{equation}
$$
$$
\begin{equation}
\nabla \times \vec E = - \frac{\partial \vec B}{\partial t}
\tag{Lei de Faraday}
\end{equation}
$$
$$
\begin{equation}
\nabla \times \vec B = \mu_0\left(\sigma \vec E +  \varepsilon_0\frac{\partial \vec E}{\partial t}\right)
\tag{Lei de Ampère}
\end{equation}
$$
