>[!info] Numeri Complessi
>Un numero complesso si può definire come una coppia ordinata di numeri reali $(a,b)$
>>L'insieme dei numeri complessi è perciò definito come il piano cartesiano
>>$$
\begin{array}
\ \mathbb{C}=\mathbb{R}\times\mathbb{R}=\mathbb{R}^2 \\
\{(a,b)|a\in\mathbb{R},b\in\mathbb{R}\}
\end{array}
>>$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---

```

#### Osservazione
- $\mathbb{R}$ è un sottoinsieme di $\mathbb{C}$ in quanto $(a,0)\to\mathbb{R}$
## Operazioni
>I numeri complessi sono dotati delle seguenti operazioni
### Somma di numeri complessi
$$
(a,b)+(c,d):=(a+c,b+d)
$$
- Elemento neutro: $(0,0)$
- Operazione opposta: $(-a,-b)$
### Prodotto di numeri complessi
$$
(a,b)\cdot(c,d):=(ac-db,ad+bc)
$$
- Elemento neutro: $(1,0)$
- Operazione opposta: $\left( \displaystyle{\frac{a}{a^2+b^2}},-\displaystyle{\frac{b}{a^2+b^2}} \right)$
#### Osservazione
$(0,1)\cdot(0,1)=(0\cdot0-1\cdot1,0\cdot1+1\cdot0) = (-1,0)$
- Quindi $(0,1)^2=-1$
	- Chiamo $(0,1)$ l'unità immaginaria e la indico con $i$

## Forma Algebrica
$$
\begin{array}
\ z\in\mathbb{C} \\
z=(a,b)=a(1,0)+b(0,1)=a+ib
\end{array}
$$
- Dove $a$ è la parte reale ($\mathbb{R}ez$)
- e b è la parte immaginaria ($Imz$)
#### Osservazione
- Osserviamo che
##### Somma
$$
\begin{array}
\ (a+ib)+(c+id)=a+c+i(c+d) \\
(a,b)+(c,d)=(a+c,b+d)
\end{array}
$$
##### Prodotto
$$
\begin{array}
\ (a+ib)\cdot(c+id)=ac-bd+i(bc+ad) \\
(a,b)\cdot(c,d)=(ac-db,ad+bc)
\end{array}
$$