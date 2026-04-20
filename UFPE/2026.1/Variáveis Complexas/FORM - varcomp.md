## 1. Números complexos e plano complexo

### Forma algébrica

$$z = x + yi, \quad x,y \in \mathbb{R}$$
$$\Re(z)=x, \quad \Im(z)=y$$

### Operações básicas

$$z_1+z_2=(x_1+x_2)+(y_1+y_2)i$$
$$z_1-z_2=(x_1-x_2)+(y_1-y_2)i$$
$$z_1z_2=(x_1x_2-y_1y_2)+(x_1y_2+x_2y_1)i$$
$$\overline{z}=x-yi$$
$$\frac{z_1}{z_2}=\frac{(x_1x_2+y_1y_2)+(y_1x_2-x_1y_2)i}{x_2^2+y_2^2}$$

### Módulo

$$|z|=\sqrt{z\overline{z}}=\sqrt{x^2+y^2}$$
$$|z_1z_2|=|z_1||z_2|$$
$$\left|\frac{z_1}{z_2}\right|=\frac{|z_1|}{|z_2|}$$

### Desigualdades úteis

$$|z_1+z_2|\le |z_1|+|z_2|$$
$$|z_1+z_2+\cdots+z_n|\le |z_1|+|z_2|+\cdots+|z_n|$$
$$\big||z_1|-|z_2|\big|\le |z_1+z_2|$$
$$\big||z_1|-|z_2|\big|\le |z_1-z_2|$$

### Forma polar e exponencial

$$x=r\cos\theta, \quad y=r\sin\theta$$
$$r=|z|=\sqrt{x^2+y^2}, \quad \theta=\arg(z)$$
$$z=r(\cos\theta+i\sin\theta)=re^{i\theta}$$
$$z_1z_2=r_1r_2\big(\cos(\theta_1+\theta_2)+i\sin(\theta_1+\theta_2)\big)$$
$$\frac{z_1}{z_2}=\frac{r_1}{r_2}\big(\cos(\theta_1-\theta_2)+i\sin(\theta_1-\theta_2)\big)$$
$$z^n=r^n\big(\cos(n\theta)+i\sin(n\theta)\big), \quad n\in\mathbb{N}$$
$$\big(\cos\theta+i\sin\theta\big)^n=\cos(n\theta)+i\sin(n\theta)$$

### Raízes

$$w_k=\sqrt[n]{r}\left(\cos\left(\frac{\theta+2k\pi}{n}\right)+i\sin\left(\frac{\theta+2k\pi}{n}\right)\right), \quad k=0,1,\ldots,n-1$$

### Fórmula de Euler

$$e^{i\theta}=\cos\theta+i\sin\theta$$

### Conjuntos no plano complexo

$$|z-z_0|=\rho$$
$$|z-z_0|\le \rho$$
$$|z-z_0|<\rho$$
$$0<|z-z_0|<\rho$$
$$\rho_1<|z-z_0|<\rho_2$$
$$\rho_1\le |z-z_0|\le \rho_2$$

## 2. Funções analíticas

### Derivada complexa

$$f'(z_0)=\lim_{z\to z_0}\frac{f(z)-f(z_0)}{z-z_0}$$

### Equações de Cauchy-Riemann

Se $$f(z)=u(x,y)+iv(x,y),$$ então
$$\frac{\partial u}{\partial x}=\frac{\partial v}{\partial y}$$
$$\frac{\partial u}{\partial y}=-\frac{\partial v}{\partial x}$$

### Derivada via Cauchy-Riemann

$$f'(z)=\frac{\partial u}{\partial x}+i\frac{\partial v}{\partial x}$$
$$f'(z)=\frac{\partial v}{\partial y}-i\frac{\partial u}{\partial y}$$

### Forma polar das equações de Cauchy-Riemann

Se $$f(z)=u(r,\theta)+iv(r,\theta),$$ então
$$\frac{\partial u}{\partial r}=\frac{1}{r}\frac{\partial v}{\partial \theta}$$
$$\frac{\partial v}{\partial r}=-\frac{1}{r}\frac{\partial u}{\partial \theta}$$

### Derivada em coordenadas polares

$$f'(z)=e^{-i\theta}\left(\frac{\partial u}{\partial r}+i\frac{\partial v}{\partial r}\right)$$
$$f'(z)=\frac{1}{r}e^{-i\theta}\left(\frac{\partial v}{\partial \theta}-i\frac{\partial u}{\partial \theta}\right)$$

### Funções harmônicas

$$\nabla^2\phi=\frac{\partial^2\phi}{\partial x^2}+\frac{\partial^2\phi}{\partial y^2}=0$$

## 3. Funções elementares complexas

### Exponencial complexa

$$e^z=e^x\cos y+ie^x\sin y$$
$$|e^z|=e^x$$
$$\arg(e^z)=y+2n\pi$$
$$\overline{e^z}=e^{\overline{z}}$$
$$e^0=1$$
$$e^{z_1}e^{z_2}=e^{z_1+z_2}$$
$$\left(e^z\right)^n=e^{nz}$$
$$e^{z+2\pi i}=e^z$$

### Logaritmo complexo

$$\ln z=\ln|z|+i\arg(z)=\ln r+i(\theta+2n\pi)$$
$$\mathrm{Ln}(z)=\ln|z|+i\mathrm{Arg}(z), \quad \mathrm{Arg}(z)\in(-\pi,\pi]$$
$$\ln(z_1z_2)=\ln z_1+\ln z_2$$
$$\ln\left(\frac{z_1}{z_2}\right)=\ln z_1-\ln z_2$$
$$\ln(z^n)=n\ln z$$
$$\left(\mathrm{Ln}\,z\right)'=\frac{1}{z}$$
$$e^{\mathrm{Ln}(z)}=z, \quad z\ne 0$$

### Funções trigonométricas complexas

$$\cos z=\frac{e^{iz}+e^{-iz}}{2}$$
$$\sin z=\frac{e^{iz}-e^{-iz}}{2i}$$
$$\sin(-z)=-\sin z$$
$$\cos(-z)=\cos z$$
$$\sin^2 z+\cos^2 z=1$$
$$\sin(z_1\pm z_2)=\sin z_1\cos z_2\pm\sin z_2\cos z_1$$
$$\cos(z_1\pm z_2)=\cos z_1\cos z_2\mp\sin z_2\sin z_1$$
$$\sin z=\sin x\cosh y+i\sinh y\cos x$$

## 4. Funções complexas e transformações

### Função complexa geral

$$f(z)=f(x+iy)=u(x,y)+iv(x,y)$$

### Representações paramétricas

Reta que passa por $$z_0$$ e $$z_1$$:
$$z(t)=z_0(1-t)+z_1t$$

Segmento de reta:
$$0\le t\le 1$$

Circunferência de centro $$z_0$$ e raio $$r$$:
$$z(t)=z_0+re^{it}, \quad 0\le t\le 2\pi$$

### Transformações lineares complexas

$$f(z)=az+b, \quad a,b\in\mathbb{C}$$

Translação:
$$T(z)=z+b$$

Rotação:
$$R(z)=az, \quad |a|=1$$

Dilatação:
$$M(z)=az, \quad a>0,\ a\in\mathbb{R}$$

### Funções potência

$$f(z)=z^n, \quad z=re^{i\theta}\mapsto w=r^ne^{in\theta}$$
$$z^{1/n}=\sqrt[n]{r}\,e^{i\arg(z)/n}$$

### Função recíproca

$$f(z)=\frac{1}{z}=\frac{1}{r}e^{-i\theta}$$

### Limites e continuidade

$$\lim_{z\to z_0}f(z)=L$$

Para todo $$\varepsilon>0$$, existe $$\delta>0$$ tal que
$$|f(z)-L|<\varepsilon \quad \text{quando} \quad 0<|z-z_0|<\delta$$

Em componentes:
$$\lim_{z\to z_0}f(z)=L \iff \lim_{(x,y)\to (x_0,y_0)}u(x,y)=u_0 \ \text{e} \ \lim_{(x,y)\to (x_0,y_0)}v(x,y)=v_0$$

Continuidade em $$z_0$$:
$$\lim_{z\to z_0}f(z)=f(z_0)$$
