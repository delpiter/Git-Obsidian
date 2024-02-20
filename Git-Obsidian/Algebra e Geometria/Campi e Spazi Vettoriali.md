### Campo
>[!info] Definizione
>Un **campo** è un insieme con due operazioni $+$ e $\cdot$ **commutative** e **associative** 
>Con **elementi neutri**, rispettivamente $0$ e $1$
>Con un **opposto** di ogni elemento $a+b = 0$
>Con **inverso** di ogni elemento non nullo $a+b = 1$

Quasi tutte le cose fatte in questo corso valgono per un campo qualsiasi
- $\mathbb{Q}$ e $\mathbb{R}$ sono dei campi
- $\mathbb{N}$ e $\mathbb{Z}$ non lo sono

>[!question] $\mathbb{C}$ è un campo?
- Si!
$$
(a+ib)-(a-ib) = a^2\cancel{+ aib }\cancel{ -aib }-i^2b^2 = a^2+b^2
$$
$$(a+ib)^{-1}=\displaystyle{\frac{a-ib}{a^2+b^2}} =1$$

### Classi
>[!info] Definizione
>Dato $n\in\mathbb{N}, n\geq 2$, e dato $a\in\mathbb{Z}$, definiamo
>$$\overline{a}= \{ b\in\mathbb{Z}  : b\equiv a (n) \}$$

- Definiamo due operazioni $+,\cdot$ su $\mathbb{Z}_{n}$ come
	- $\overline{a}+\overline{b} = \overline{a+b}$
	- $\overline{a}\cdot \overline{b} = \overline{a\cdot b}$

#### Es
In $\mathbb{Z}_{3}$
- $\overline{1}+\overline{2} = \overline{0}$
- $1+2 =3 \equiv 0 (3)$

In $\mathbb{Z}_{5}$
- $\overline{3}\cdot \overline{4} = \overline{2}$ perhchè $3\cdot4=12\equiv 2(5)$

#### Osservazione
$\mathbb{Z}_{n}$ è un campo $\Leftrightarrow n$ è **primo**

## Spazio Vettoriale
---
>[!info] Definizione
>Sia $k$ un campo
>Uno **Spazio Vettoriale** su $k$ è un insieme $V$ con 2 operazioni
>>[!tip] Somma di Vettori ($+$)
>>Associa due elementi di $V$ ad un altro elemento di $V$
>>>$v_{1},v_{2}\in V$ associa $v_{1}+v_{2}\in V$
>>
>>Soddisfa le seguenti **proprietà**:
>>- Commutativa
>>- Associativa
>>- Ha un numero neutro $\underline{0}$ e opposti
>
>>[!tip] Prodotto scalare ($\cdot$)
>>Operazione che a $a \in k, v\in V$ associa $a\cdot v\in V$
>>Soddisfa le seguenti **proprietà**
>>- Associativa
>>- Distributiva rispetto alla somma 
>>- Ha un elemento neutro

### Proprietà Somma
1. Proprietà Commutativa$$v_{1}+v_{2} = v_{2}+v_{1}, \forall v_{1},v_{2} \in V$$
2. Proprietà Associativa$$(v_{1}+v_{2})+v_{3}=v_{1}+(v_{2}+v_{3}),\forall v_{1},v_{2},v_{3}\in V$$
3. Elemento Neutro $$\exists \underline{0}\in V (\text{"vettore nullo"}):\underline{0}+v = v \ \forall v \in V$$
4. Elementi Opposti $$\forall v\in V, \exists -v\in V : v+(-v)=\underline{0}$$
### Proprietà Prodotto
$\forall\ v,v_{1},v_{2} \in V, \forall a,b \in k$
5. Proprietà Associativa $$a(bv)=(ab)v$$
6. Proprietà Distributiva 
$$
\begin{array}
\ (a+b)v = av +bv \\
a(v_{1}+v_{2}) = av_{1}+av_{2}
\end{array}
$$
7. Elemento Neutro $$1v=v$$

### Esempi
1. Vettori **Geometrici**
![[Pasted image 20240219172214.png]]

2. Dato un campo $k$, $n\geq 1$
$$
V=k^n = \{ (x_{1},x_{2},\dots,x_{n}), x_{i}\in k, \forall i=1,2,3,\dots,n \}
$$
- È uno **spazio vettoriale** su $k$ rispetto alle operazioni:
$$
\begin{array}
\ v_{1}=(x_{1},x_{2},\dots,x_{n}),v_{2}=(y_{1},y_{2},\dots,y_{n}) \\
v_{1}+v_{2} = (x_{1}+y_{1},x_{2}+y_{2},\dots,x_{n}+y_{n}) \\
av_{1}=(ax_{1},ax_{2},\dots,ax_{n})
\end{array}
$$
- Vettore "vuoto" $\underline{0}=(0,0,0,\dots,0)$

3. Polinomio
$\mathbb{K}[x]={\text{ polinomi a coefficientni in } \mathbb{K}}$

###### Es
$p(x)=2x^2-1, q(x)=x^3-3x+2 \in\mathbb{R}[x]$
$(p+q)(x)=x^3+2x^2-3x+1$
$\left(  \frac{5}{2} p\right )(x)=5x^2- \frac{5}{2}$

4. Funzioni
Sia $X$ un insieme
$V=\{ \text{funzioni }X\to \mathbb{K}\}$
- È uno spazio vettoriale rispetto alle operazioni:
	- $(f+g)(x)=f(x)+g(x)$
	- $(af)(x) = af(x)$

5. $\mathbb{C}$ è uno spazio vettoriale sul campo $\mathbb{R}$
Se $z_{1}=a+ib,z_{2}=c+id \in\mathbb{C}$
- $z_{1}+z_{2}= (a+c)+i(b+d)\in \mathbb{C}$

Sia $h\in\mathbb{R}, hz_{1}=ha+ihb$

### Riassunto
Dato uno spazio vettoriale $V$ su un campo $\mathbb{K}$ chiamiamo *scalari* gli elementi del campo $\mathbb{K}$

Chiamiamo invece *vettori* gli elementi dello spazio vettoriale $V$

#### Riepilogo esempi
- Nell'esempio `1` un vettore è una **freccia**
- Nell'esempio `2` un vettore è una **$n$-upla di numeri**
- Nell'esempio `3` un vettore è un **polinomio**
- Nell'esempio `4` un vettore è una **funzione**
- Nell'esempio `5` un vettore è un **numero complesso**

## Sottospazio Vettoriale
---
>[!info] Definizione
>Sia $\mathbb{K}$ un *campo* e sia $V$ uno *spazio vettoriale* su $\mathbb{K}$
>Un **Sottospazio Vettoriale** di $V$ è un sottoinsieme $U$ di $V$ non vuoto che è chiuso rispetto a tali operazioni
>>[!done] Cioè
>>$$U\subseteq V:\ \forall v_{1},v_{2}\in U,v_{1}+v_{2}\in U$$
>>e
>>$$\forall a \in\mathbb{K}, \forall v\in U, av\in U$$

### Esempi
#### Esempio 1
>Sia $\mathbb{K}=\mathbb{R}, V=\mathbb{R}^2=\{ (x,y):x,y\in\mathbb{R} \}$
>$U=\{ (x,y)\in\mathbb{R}^2 :y =2x\}$

>[!question] $U$ è un sottospazio vettoriale??

$$
\begin{array}
\ v_{1}=(x,2x)\ \ \ \ v_{2}=(x',2x') \in U \\
v_{1}+v_{2} = (x+x', 2(x+x'))\in U \\
av_{1} = a(x,2x) = (ax,2ax)\in U
\end{array}
$$
>[!done] Si, $U$ è un sottospazio vettoriale di $V$

#### Esempio 2
> $\mathbb{K}=\mathbb{R}, V = \mathbb{R}^2, S = \{ (x,y)\in\mathbb{R}^2 :xy\geq0\}$

>[!question] $S$ è un sottospazio vettoriale??

$$
\begin{array}
v_{1}=(1,2),v_{2}=(-2,-1)\in S \\
v_{1}+v_{2} = (-1,1) \cancel{ \in }S
\end{array}
$$
![[Pasted image 20240220175558.png]]
>[!error] No, $S$ non è un sottospazio vettoriale di $V$

#### Esempio 3
>Sia $V=\mathbb{R}[x]=\{ \text{polinomi a coefficienti in } \mathbb{R}\}$
>Sia $U=\{ \text{ polinomi di grado }2 \}$

>[!question] $U$ è un sottospazio vettoriale??

$$
p_{1}(x)=x^2-3x+4 \in U, p_{2}(x) = -x^2 +2x-3 \in U
(p_{1}+p_{2})(x) = -x+1 \cancel{ \in } U
$$
>[!error] No, $U$ non è un sottospazio vettoriale di $V$

> Sia invece $W=\{ \text{ polinomi di grado }\leq 2 \}=\{ a,b,c\in\mathbb{R} :ax^2+bx+c\}$

$$
p_{1}=ax^2+bx+c ,p_{2}=a'x^2+b'x+c
p_{1}+p_{2}=(a+a')x^2+(b+b')x+(c+c')
$$
- E analogamente l'altra operazione
>[!done] Si, $W$ è un sottospazio vettoriale di $V$

#### Esempio 4
>$\mathbb{K}=\mathbb{R},V=\{ \text{ funzioni }f:\mathbb{R}\to\mathbb{R} \}$
>$U=\{ \text{ funzioni continue } f:\mathbb{R}\to\mathbb{R} \}$

>[!done] $U$ è un sottospazio vettoriale di $V$ poichè somma e prodotto di funzioni continue è essa stessa una funzione continua

### Proprietà
>[!info] Definizione
>$U$ è un **sottospazio vettoriale** di $V \Leftrightarrow \forall v_{1},v_{2}\in U,\forall a_{1},a_{2}\in \mathbb{K}, a_{1}v_{1}+a_{2}v_{2}\in U$ 

>[!tip] Dimostrazione

>$\implies$

Siano $v_{1},v_{2} \in U$ e $a_{1},a_{2} \in \mathbb{K}$
- Poichè $U$ è un *sottospazio vettoriale*, $a_{1}v_{1},a_{2}v_{2} \in U \implies a_{1}v_{1}+a_{2}v_{2}\in U$

>$\impliedby$

Siano $v_{1},v_{2}\in U$ poichè $a_{1}v_{1}+a_{2}v_{2}\in U \forall a_{1},a_{2} \in \mathbb{K}$
- Scegliendo $a_{1}=1,a_{2}=1$ ho che $v_{1}+v_{2}\in U$
- Scegliendo $a_{2}=0$ ho che $a_{1}v_{1}\in U \forall a_{1}\in\mathbb{K}$