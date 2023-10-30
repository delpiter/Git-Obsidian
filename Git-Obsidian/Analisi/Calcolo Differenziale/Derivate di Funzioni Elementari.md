## Monomio
---
>[!tip] Funzione
>$$f(x) = x^n, n\in\mathbb{N}$$
- Utilizzando la [[Definizioni_Analisi#Formula del Binomio di Newton|formula del binomio di newton]] voglio calcolare $f'(c), \forall c\in\mathbb{R}$
### Dimostrazione
$$
\begin{array}
\ \lim\limits_{h\to 0 } \displaystyle{\frac{(c+h)^n-c^n}{h}} = \lim\limits_{h\to 0} \displaystyle{\frac{\displaystyle\left( \sum^n_{k=0} \binom{n}{k}c^{n-k}h^k\right)-c^n}{h}} = \\
=\lim\limits_{h\to 0} \displaystyle{\frac{\cancel{ c^n }+n c^{n-1}h+\displaystyle\left( \sum^n_{k=2} \binom{n}{k}c^{n-k}h^k\right)-\cancel{ c^n }}{h}} =
\end{array}
$$
- Poichè la somma per $h\to 0$ tende a 0 ho:
$$
\displaystyle{\frac{n\cdot c^{n-1}\cdot h}{h}} = nc^{n-1}
$$
## Esponenziale
---
>[!tip] Funzione
>$$f(x)=e^x, c\in\mathbb{R}$$

### Dimostrazione
$$f'(c)=\lim\limits_{x\to c} \displaystyle{\frac{e^x-e^c}{x-c}}=\lim\limits_{x\to c} \displaystyle{\frac{e^c(e^x-c-1)}{x-c}} = e^c$$
## Teorema dell'algebra delle Derivate
---
>[!info] Teorema
>Sia $I$ intervallo di $\mathbb{R}$, $f,g:I\to\mathbb{R},c\in I,k\in\mathbb{R}$
>Se $f,g$ sono entrambe derivabili in $c$
><u>Allora</u>
>$(f+g)'(c)=f'(c)+g'(c)$
>$(f\cdot g)'(c)=f'(c)\cdot g(c)+f(c)\cdot g'(c)$
>$\displaystyle{\left( \frac{f}{g}\right)(c)}= \displaystyle{\frac{f'(c)\cdot g(c)-f(c)\cdot g'(c)}{(g(c))^2}}, g(c)\neq0$
>$(kf)'(c) = kf'(c)$

### Dimostrazione Proprietà 1
### Dimostrazione  Proprietà 2
$$
\begin{array}
\ \displaystyle{\frac{(f\cdot g)(x)-(f\cdot g)(c)}{x-c}}=\displaystyle{\frac{f(x)g(x)-f(x)g(c)+f(x)g(c)-f(c)g(c)}{x-c}}= \\
= f(x)\displaystyle{\frac{(g(x)-g(c))}{x-c}}+g(c) \displaystyle{\frac{(f(x)-f(c))}{x-c}}
\end{array}
$$
- Passiamo al limite per $x\to c$
$$
\lim\limits_{x\to c} \underbrace{ f(x) }_{ f(c) }\underbrace{ \displaystyle{\frac{(g(x)-g(c))}{x-c}} }_{ g'(x) }+g(c) \underbrace{ \displaystyle{\frac{(f(x)-f(c))}{x-c}} }_{ f'(x) }
$$
### Dimostrazione Proprietà 3

## Derivate di Funzioni Composte
---
>[!info] Teorema
>Siano $I,J$ [[Introduzione Funzioni#Intervallo|intervalli]] di $\mathbb{R}$, $f:I\to\mathbb{R}$, $g:J\to\mathbb{R},f(I)\subseteq J$
>Sia $c\in I$
>Supponiamo $f$ derivabile in $c$ e $g$ sia derivabile in $f(c)$
><u>Allora</u>
>$$(g_{o}f)'(c)=g'(f(c))f'(c)$$
### Dimostrazione
$$
\displaystyle{\frac{(g_{o}f)(x)-(g_{o}f)(c)}{x-c}}= \displaystyle{\frac{g(f(x))-g(f(c))}{x-c}}
$$
- Per ipotesi $g$ è derivabile in $f(c)$ e dunque per il [[Derivate#Teorema di Caratterizzazione delle Funzioni Derivabili|teorema di caratterizzazione di funzioni derivabili]] si ha:
$$
g(y) = g(f(c))+g'(f(c))\cdot (y-f(c))+\circ(y-f(c)) \text{ per }y\to f(c)
$$
- Posso sostituire $y=f(x)$ infatti: $f(x)\to f(c) \text{ per } x\to c$ poichè $f$ è continua
$$
g(f(x)) = g(f(c))+g'(f(c))\cdot (f(x)-f(c))+\circ(f(x)-f(c)) \text{ per }f(x)\to f(c)
$$
- Applico la definizione di derivata
$$
\begin{array}
\ 
\lim\limits_{x\to c} \displaystyle{\frac{\cancel{ g(f(c)) }+g'(f(c))\cdot (f(x)-f(c))+\circ(f(x)-f(c))-\cancel{ g(f(c)) }}{x-c}}= \\
= \lim\limits_{x\to c}g'(f(c))\cdot\underbrace{  \displaystyle{\frac{f(x)-f(c)}{x-c}} }_{ f'(c) } = g'(f(c))f'(c)
\end{array}
$$
## Derivata della Funzione Inversa
---
>[!info] Teorema
>Sia $I$ [[Introduzione Funzioni#Intervallo|intervallo]] di $\mathbb{R}$, $f:I\to\mathbb{R}$ invertibile e derivabile in $c\in I$
>Supponiamo $f'(c)\neq 0$
><u>Allora</u>
>Posto $y=f(c)$, si ha:
>$$(f^{-1})'(y)= \displaystyle{\frac{1}{\underbrace{ f'(f^{-1}(y)) }_{ c }}}$$

## Funzioni Trigonometriche
---
### Seno
>[!tip] Funzione
>$$f(x)=sen(x)$$

#### Dimostrazione
$$
\begin{array}
\ f'(c)=\lim\limits_{h\to 0} \displaystyle{\frac{sen(c+h)-sen(c)}{h}}= \\
\lim\limits_{h\to 0} \displaystyle{\frac{sen(c)cos(h)+sen(h)cos(c)-sen(c)}{h}}= \\
= \lim\limits_{h\to 0} sen(c)\displaystyle{\underbrace{ \frac{(cos(h)-1)}{h} }_{ 0 }}+\displaystyle{\underbrace{ \frac{sen(h)}{h} }_{ 1 }cos(c)} = cos(c)
\end{array}
$$
### Coseno
>[!tip] Funzione
>$$f(x)=cos(x)$$
#### Dimostrazione
$$
\begin{array}
\ f'(c)= \lim\limits_{h\to 0} \displaystyle{\frac{cos(c+h)-cos(c)}{h}} = \lim\limits_{h\to 0} \displaystyle{\frac{cos(c)cos(h)-sen(c)sen(h)-cos(c)}{h}} \\
\lim\limits_{h\to 0} cos(c)\displaystyle{\frac{cos(h)-1}{h}}- \displaystyle{\frac{sen(c)sen(h)}{h}}
\end{array}
$$