## Operazioni Macchina
---
>[!example] Operazioni sui [[Floating Point]]
>$fl(x)\oplus fl(y)=fl(fl(x)+fl(y))$
>$fl(x)\ominus fl(y)=fl(fl(x)-fl(y))$
>$fl(x)\otimes fl(y)=fl(fl(x)\cdot fl(y))$
>$fl(x)\oslash fl(y)=fl(fl(x) / fl(y))$

## Propagazione degli Errori nella Somma
---
>[!summary] Somma
>Assumiamo $x,y\in \mathbb{R}$, ma $x,y\notin F$
>- $x$ e $y$ devono essere arrotondati in $F$:
>$x \to fl(x)=x(1+\mathcal{E}_{x})\in F$
>$y \to fl(y)=y(1+\mathcal{E}_{y})\in F$
>
>I due numeri di $F$ vengono quindi ***sommati***, ottenendo:
>$$fl((fl(x))\oplus(fl(y)))=[x(1+\mathcal{E}_{x})+y(1+\mathcal{E}_{y})](1+\mathcal{E}_{s})$$
>
>Con:
>- $\mid\mathcal{E}_{x}\mid,\mid\mathcal{E}_{y}\mid,\mid\mathcal{E}_{s}\mid \leq u$

#### Errore Relativo
>Il risultato finale sarà $[x(1+\mathcal{E}_{x})+y(1+\mathcal{E}_{y})](1+\mathcal{E}_{s})$ da confrontare con il vero risultato $x+y$.

$$
Err_{rel_{s}}=\displaystyle{\frac{\mid[x(1+\mathcal{E}_{x})+y(1+\mathcal{E}_{y})](1+\mathcal{E}_{s})-(x+y)\mid}{\mid x+y\mid}}=
$$
$$
=\displaystyle{\frac{\mid \cancel{ x }+x\mathcal{E}_{s}+x\mathcal{E}_{x}\mathcal{E}_{s}\cancel{ +y }+y\mathcal{E}_{s}+y\mathcal{E}_{y}\mathcal{E}_{s}\cancel{ -(x+y) }\mid}{\mid x+y\mid}}
$$

- Assumendo che la [[Floating Point#Conclusioni|roundoff unit]] "$u$" sia molto più piccola di $1$, in modo da poter trascurare $u^2$ rispetto a $u$.

$$
Err_{rel_{s}}\approx \left| \displaystyle{\frac{x}{x+y}\mathcal{E}_{x}}+\displaystyle{\frac{y}{x+y}\mathcal{E}_{y}}  +\mathcal{E}_{s}\right|\leq \left|\displaystyle{\frac{x}{x+y}}\right|u+\left|\displaystyle{\frac{y}{x+y}}\right|u + u 
$$

>[!todo] $x$ e $y$ hanno lo stesso segno

Allora $\left|\displaystyle{\frac{x}{x+y}}\right|,\left|\displaystyle{\frac{y}{x+y}}\right|\leq 1$.
- E di conseguenza:

$$Err_{rel_{s}}\leq 3u$$

>[!caution] $x$ e $y$ hanno segno diverso

Le quantità $\left|\displaystyle{\frac{x}{x+y}}\right|$ e $\left|\displaystyle{\frac{y}{x+y}}\right|$ possono assumere ***qualunque grandezza***, quindi **non possiamo controllare l'errore a priori**.

