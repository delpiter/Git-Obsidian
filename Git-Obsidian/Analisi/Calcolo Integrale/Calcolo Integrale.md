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