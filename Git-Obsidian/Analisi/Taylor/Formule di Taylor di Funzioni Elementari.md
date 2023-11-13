## Esponenziale
---
>[!tldr] Funzione
>$$f(x)=e^x$$
>Derivabile $n$ volte $\forall n \in\mathbb{N}$ su tutto $\mathbb{R}$

### Dimostrazione
Calcoliamo $T_{c,n}(x)$ con $c=0$
- $f'(0)=e^0=1$
- $f''(0)=e^0=1$
- $f'''(0)=e^0=1$
- $f^{(n)}(0)=e^0=1$
#### Applico il polinomio di Taylor
$$
T_{c,n}(x)=\sum^n_{k=0} \displaystyle{\frac{1}{k!}}(x)^k=1+x+\displaystyle{\frac{x^2}{2}}+\displaystyle{\frac{x^3}{3}}+\displaystyle{\frac{x^4}{4}}\dots +\displaystyle{\frac{x^n}{n}}
$$
#### Formula di Taylor
>[!tldr] Formula
>$$e^x=1+x+\displaystyle{\frac{x^2}{2}}+\displaystyle{\frac{x^3}{3}}+\displaystyle{\frac{x^4}{4}}\dots +\displaystyle{\frac{x^n}{n}}+\circ(x^n)$$

## Logaritmo
---
>[!tldr] Funzione
>$$f(x)=ln(x+1)$$
### Dimostrazione
Calcoliamo $T_{c,n}(x)$ con $c=0$
- $f'(0)=\displaystyle{-\frac{1}{1+x}}=1$
- $f''(0)=\displaystyle{-\frac{1}{(1+x)2}}=-1$
- $f'''(0)=\displaystyle{\frac{2}{(1+x)^3}}=2$
- $f^{(4)}(0)=\displaystyle{\frac{-2\cdot3}{(1+x)^4}}=-2\cdot3$
- $f^{(n)}(0)=-2\cdot 3\cdot (-4)\cdot 5\dots \pm n$
#### Formula di Taylor
>[!tldr] Formula
>$$ln(1+x)=x- \displaystyle{\frac{1}{2}}x^2+ \displaystyle{\frac{1}{3}}x^3- \displaystyle{\frac{1}{4}}x^4\dots \pm \displaystyle{\frac{1}{n}}x^n+\circ(x^n)$$
## Seno
---
### Dimostrazione
Calcoliamo $T_{c,n}(x)$ con $c=0$
- $f'(0)=cos(0)=1$
- $f''(0)=-sen(0)=0$
- $f'''(0)=-cos(0)=-1$
>[!done] In breve
>I coefficienti con indici corrispondenti a ordine di derivazione pari sono uguali a $0$
>I coefficienti con indici corr. a ordine di derivazione dispari si alternano fra $1$ e $-1$
#### Applico il polinomio di Taylor
$$
T_{c,n}(x)=\sum^n_{k=0} \displaystyle{\frac{(-1)^n}{(k^{2n+1})!}}(x)^{2k+1}=x-\displaystyle{\frac{x^3}{3!}}+\displaystyle{\frac{x^5}{5!}}-\displaystyle{\frac{x^7}{7!}}\dots \pm\displaystyle{\frac{x^{2n+1}}{(2n+1)!}}
$$
#### Formula di Taylor
>[!tldr] Formula
>$$sen(x)=x-\displaystyle{\frac{x^3}{3!}}+\displaystyle{\frac{x^5}{5!}}-\displaystyle{\frac{x^7}{7!}}\dots \pm\displaystyle{\frac{x^{2n+1}}{(2n+1)!}}\circ(x^{n+1})$$

## Coseno
---
### Dimostrazione
Calcoliamo $T_{c,n}(x)$ con $c=0$
- $f'(0)=-sen(0)=0$
- $f''(0)=-cos(0)=-1$
- $f'''(0)=sen(0)=0$
>[!done] In breve
>I coefficienti con indici corrispondenti a ordine di derivazione dispari sono uguali a $0$
>I coefficienti con indici corr. a ordine di derivazione pari si alternano fra $1$ e $-1$
#### Applico il polinomio di Taylor
$$
T_{c,n}(x)=\sum^n_{k=0} \displaystyle{\frac{\pm1}{(n)!}}(x)^{2n}=1- \displaystyle{\frac{x^2}{2}}+ \displaystyle{\frac{x^4}{4!}}- \displaystyle{\frac{x^6}{6!}}\dots \pm\displaystyle{\frac{x^{2n}}{(2n)!}}
$$
#### Formula di Taylor
>[!tldr] Formula
>$$cos(x)=1- \displaystyle{\frac{x^2}{2}}+ \displaystyle{\frac{x^4}{4!}}- \displaystyle{\frac{x^6}{6!}}\dots \pm\displaystyle{\frac{x^{2n}}{(2n)!}}\circ(x^{n+1})$$
