## Definizione Integrale
---
>[!info] Definizione
>Sia $f:[a,b]\to\mathbb{R}$ una funzione e tale che $f(x)\geq0,\forall x \in[a,b]$
>Chiamiamo sottografico di $f$, l'insieme:
>$$ \large \Gamma f = \{ (x,y) \in \mathbb{R} \times \mathbb{R} \mid x \in [a,b], y \in [0, f(x)] \} $$

![[Pasted image 20231115133900.png]]

### Osservazione
$$
(b-a)\cdot \inf\limits_{[a,b]}f\leq Area(\Gamma_{f})\leq (b-a)\cdot \sup\limits_{[a,b]}f
$$
![[Pasted image 20231115133951.png]]

Analogamente, se suddivido $[a,b]$ in $n$ parti uguali $[x_{i-1},x_{i}]$, posso dire che:
$$
\sum^n_{i=1}(x_{i}-x_{i-1})\cdot \inf\limits_{[x_{i-1},x_{i}]}f\leq Area(\Gamma_{f})\leq \sum^n_{i=1}(x_{i}-x_{i-1})\cdot \sup\limits_{[x_{i-1},x_{i}]}f
$$
![[Pasted image 20231115144148.png]]
## Integrale di Funzioni Continue
---
>[!info] ?
>Sia $f:[a,b]\to\mathbb{R}$ [[Introduzione Funzioni#Continuità|continua]]
>Suddivido $[a,b]$ in $n$ intervalli della forma $[x_{i-1},x_{i}]$ dove:
>$$
\begin{cases}
x_{0} = a  \\
x_{n}=b \\
x_{i}-x_{i-1} = \displaystyle{\frac{b-a}{n}}
\end{cases}
>$$

### Somma di RIEMANN di $f$
>[!info] ?
>Sia $c_{i}\in[x_{i-1},x_{i}] \forall i =1,2,3,\dots,n$
>Chiamiamo somma di RIEMANN di $f$
>$$S_{R}(f,c_{1},c_{2},\dots,c_{n})=\sum^n_{i=1}f(c_{i})\cdot \displaystyle{\frac{b-a}{n}}$$

>[!info] Teorema
>Sia $f:[a,b]\to\mathbb{R}$ [[Introduzione Funzioni#Continuità|continua]]
><u>Allora</u>
>$$\exists \lim\limits_{n\to +\infty}S_{R}(f,c_{1},c_{2},\dots,c_{n})\in\mathbb{R}$$
>E non dipende dalla scelta di $c_{i}$
>
>>[!tldr] Definizione
>>Chiamiamo tale limite **integrale** di $f$ in $[a,b]$ e lo indichiamo con:
>>$$ \large \int_{a}^{b} f(x) dx$$

