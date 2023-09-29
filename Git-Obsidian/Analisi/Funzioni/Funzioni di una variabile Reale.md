## Costanti
- - -
>[!info] Definizione
>$$
\begin{array}
/f : \mathbb{R} \to \mathbb{R} \\
f(x) =k, \; k \in \mathbb{R}
\end{array}
>$$

$$
 

$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---
y=7
```
## Polinomi
- - -
>[!info] Definizione
>$$
\begin{array}
/f: \mathbb{R} \to \mathbb{R} \\
f(x) = ax^p+bx^{p-1}+\dots+ax+a \\
p \in \mathbb{N} \\
\end{array}
>$$
###### Es
$f(x)=3x^4-2x^2+2x+1$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-3,3,-3,3]
disableZoom: true
grid: true
---
y=3x^4-2x^2+2x+1
```
## Valore assoluto
- - -
>[!info] [[Breve ripasso#Valore assoluto|Definizione]]
>$$
\begin{array}
/f: \mathbb{R} \to \mathbb{R} \\
f(x)=|x|
\end{array}
>$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-3,3,-3,3]
disableZoom: true
grid: true
---
y=abs(x)
```
## Funzione Segno
- - -
>[!info] Definizione
>$$
\begin{array}
/f: \mathbb{R}\setminus \{0\} \to \mathbb{R} \\ \\
f(x)=segno(x)=\begin{cases}
1\;\text{se}\;x>0 \\
-1\;\text{se}\;x<0
\end{cases}
\end{array}
>$$


```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-2,2,-2,2]
disableZoom: true
grid: true
---
f(x)=sign(x)
```
## Parte intera
- - -
>[!info] Definizione
>$$
\begin{array}
/f(x)=\lfloor x \rfloor \\
f:\mathbb{R}\to\mathbb{R} \\
f:=max\{z \in\mathbb{Z}|z\leq x\}
\end{array}
>$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-5,5,-5,5]
disableZoom: true
grid: true
---
f(x)=floor(x)
```
## Funzione Periodica
- - -
### Parte Frazionaria
>[!info] Definizione
>$$
\begin{array}
/f:\mathbb{R}\to\mathbb{R} \\
f(x)=x-\lfloor x \rfloor
\end{array}
>$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-4,4,-4,4]
disableZoom: true
grid: true
---
f(x)=x-floor(x)
```
## Funzione Esponenziale
>[!info] Definizione
>$a^p, p\in\mathbb{Q}$
>Per la priprietà di densità di $\mathbb{Q}$ in $\mathbb{R}$, posso estendere tale definizione da $p \in \mathbb{Q}$ a $p \in \mathbb{R}$

### Proprietà
- Sempre strettamente positiva ($a^x>0, \forall x \in \mathbb{R}$)
- $a^{x+y}=a^x\cdot a^y$
- $(a^x)^y=a^{x\cdot y}$
- $a^x\cdot b^x=(ab)^x\ \ \ \ \ \ \ \ a,b\in\mathbb{R}^+\setminus\{0,1\}$
- Se $a >1$
	- $exp_{a}$ è [[Intro#Crescente|strettamente crescente]]
- Se $0<a<1$
	- $exp_{a}$ è [[Intro#Decrescente|strettamente descrescente]]
- $exp_{a}:\mathbb{R}\to\mathbb{R}^+\setminus\{0\} \to$ [[Intro#Iniettività e surriettività|Invertibile]]
### Grafici
$$
\boxed{a>1}
$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---
f(x)=2^x
```
$$
\boxed{0<a<1}
$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---
f(x)=(1/2)^x
```
## Funzione Logaritmica
- - -
>[!info] Definizione
>Sia $a \in \mathbb{R}^+ \setminus\{0,1\}$, chimamiamo **Logaritmo** in base $a$, la funzione inversa di $exp_{a}$ e lo indico con:
>$$
>log_{a}:=(exp_{a})^{-1} \ \ \ \ \ \ [log_{a}:\mathbb{R}^+\setminus{0}\to \mathbb{R}]
>$$
### Proprietà
- $\forall x,y \in \mathbb{R}^+\setminus\{0\}, \log_{a}(x\cdot y)=\log_{a}x + \log_{a}y$
- $\log_{a}x^\alpha=\alpha\log_{a}x \ \ \ \ \ \alpha\in\mathbb{R}$

#### Dimostrazione proprietà 1
> Voglio dimostrare che $\log_{a}(x\cdot y)=\log_{a}x+\log_{a}y$
- Per la proprietà della [[Intro#Funzione Identità|funzione identità]]
	- $\huge{a^{\log_{a}(x\cdot y)}=a^{\log_{a}x}\cdot a^{\log_{a}y}}$
	- Per la proprietà della funzione esponenziale
	- $\huge{a^{\log_{a}x}\cdot a^{\log_{a}y}=a^{\log_{a}x+\log_{a}y}}$
	- Poichè la funzione è iniettiva i due esponenti devono essere per forza uguali
### Grafici
$$
\boxed{a>1}
$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---
f(x)=log(x)
```
$$
\boxed{0<a<1}
$$

```functionplot
---
title: 
xLabel: 
yLabel: 
bounds: [-10,10,-10,10]
disableZoom: true
grid: true
---
f(x)=log(x)/log(1/2)
```
#### Osservazione
- Esponenziale e logaritmo sono specchiati rispetto alla bisettrice
	- In generale $f$ e $f^{-1}$ sono simmetriche rispetto alla retta $y=x$

## Funzioni trigonometriche