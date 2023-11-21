## Teorema Fondamentale del Calcolo Integrale
---
>[!info] Teorema
>Sia $f\in C^1([a,b],\mathbb{R})$
><u>Allora</u>
>$$\int _{a}^b f'(x)\, dx =f(b)-f(a)$$

### Dimostrazione

Si ha che:
$$
f(b)-f(a) = \underbrace{ \sum^n_{i=1}(f(x_{i})-f(x_{i-1})) }_{ \text{Somma Telescopica} }
$$

Per il [[Teoremi basati sulle Derivate#Teorema di Lagrange|teorema di Lagrange]]
$\exists c_{i}\in[x_{i},x_{i-1}]:$
$$
\underbrace{ \sum^n_{i=1}(f'(c_{i})(x_{i}-x_{i-1})) }_{\text{Def. Somma Reiman} }
$$
- Passo al limite
$$
f(b)-f(a)=\int _{a}^b f'(x) \, dx 
$$
## Integrazione per Parti
---
>[!info] Teorema
>Sia $f\in C([a,b],\mathbb{R})$ e sia $g\in C^1([a,b],\mathbb{R})$
>Sia $F$ una primitiva di $f$
><u>Allora</u>
>$$\int _{a}^b f(x)g(x) \, dx = [F(x)g(x)]_{a}^b - \int _{b}^a F(x)-g'(x)\, dx  $$

### Dimostrazione
Considero
$$
(F\cdot g)'(x) = F'(x)g(x)+F(x)g'(x)
$$
- Integro
$$
\underbrace{ \int _{a}^b (Fg)'(x)dx\, dx }_{ \displaystyle [F(x)g(x)]_{a}^b } = \int _{a}^b \underbrace{ F'(x) }_{ f(x) }g(x) \, dx + \int _{a}^b F(x)g'(x)\, dx  
$$
Quindi
$$
\int _{a}^b { f(x) }g(x)\,dx = [F(x)g(x)]_{a}^b -\int _{a}^b F(x)g'(x)\, dx
$$
## Integrazione per Sostituzione
---
>[!info] Teorema
>Siano $I,J$ [[Introduzione Funzioni#Intervallo|intervalli]] di $\mathbb{R}$
>Siano $f\in C(I,\mathbb{R}),\varphi\in C^1(J,I)$
><u>Allora</u>
>1) Se $\alpha,\beta\in J$$$\int _{\alpha}^\beta f(\varphi(t))\varphi'(t)\, dt = \int _{\varphi(\alpha)}^{\varphi(\beta)} f(x)\, dx  $$
>2) Se $\varphi:J\to I$ è invertibile, siano $a,b\in I$ $$\int _{a}^b f(x) \, dx = \int _{\varphi^{-1}(a)}^{\varphi^{-1}(b)} f(\varphi(t))\varphi'\, dx  $$

### Dimostrazione
Sia $F$ una primitiva di $f$
- Considero $F_{o}\varphi$ e la derivo
$$
(F_{o}\varphi)'(t)=F'(\varphi(t))\cdot \varphi'(t)=f(\varphi(t))\cdot \varphi'(t)
$$
- Integro fra $\alpha$ e $\beta$
$$
\int _{\alpha}^\beta (F_{o}\varphi)'(t)\, dx = \int _{\alpha}^\beta f(\varphi(t))\cdot \varphi'(t)\, dx 
$$
- Usando il teorema fondamentale di Integrazione
$$
\int _{\varphi(\alpha)}^{\varphi(\beta)} f(x) \, dx =F(\varphi(\beta))-F(\varphi(\alpha)) =\int _{\alpha}^\beta (F_{o}\varphi)'(t)\, dx = \int _{\alpha}^\beta f(\varphi(t))\cdot \varphi'(t)\, dx 
$$