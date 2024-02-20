La [[Concetti Base#Insieme|terminologia]] degli insiemi è sempre la stessa

## Relazione
>[!info] Definizione
> Una **relazione** su un insieme $A$ è un sottoinsieme $\mathbb{R}$ di $A\times A$
> Scrivo $a_{1}Ra_{2}$ se $(a_{1},a_{2}) \in\mathbb{R}$ e dico: *"$a_{1}$ è in relazione con $a_{2}$"*

Una relazione $R$ è una **relazione di equivalenza** se valgono le seguenti proprietà:
>[!tip] Proprietà Riflessiva
>$$aRa \forall a \in A$$
>
>>[!done] In Breve
>> Possiamo dire che ogni elemento è in **relazione con se stesso**

>[!tip] Proprietà Simmetrica
>$$aRb \implies bRa \ \ (\forall a,b \in A)$$
>
>>[!done] In Breve
>> Se un elemento è in **relazione con un altro** vale anche il viceversa, cioè che l'altro elemento è in **relazione** con il primo elemento

>[!tip] Proprietà Transitiva
>$$aRb, bRc \implies aRc \ \ (\forall a,b,c \in A)$$
>a
>>[!done] In Breve
>>Considerando le due relazioni $aRb$ e $bRc$ di conseguenza vale anche la relazione $aRc$

- Essere uguali è una relazione di equivalenza

### Esempi
- Uguaglianza fra Numero
- Avere la stessa età in un gruppo di persone
- Parallelismo tra rette (*coincidenti*)
### Controesempi
- Disuguaglianza
- Gruppo di persone che abitano tutte a meno di 10 km di distanza
- L'amicizia
- Perpendicolarità

## Congruenza a Modulo $n$
---
>[!info] Definizione
>Sia $n\in\mathbb{Z}, n\geq2$, siano $a,b\in\mathbb{Z}$
>$$a \equiv b (n)$$
>Se $a-b$ è multiplo di $n$ cioè
>$$\exists h\in\mathbb{Z}:a-b=h(n)$$
>Si dice
>- "$a$ congruo a $b$ modulo $n$"

 Essere **congrui a modulo $n$** è una relazione di equivalenza 
 #### Dimostrazione
 >[!done] Proprietà Riflessiva
 $$\forall a \in\mathbb{Z}, a\equiv a (n) \implies a-a = 0 = 0\cdot n$$

>[!done] Proprietà Simmetrica
>Se $a\equiv b\ (n)$ allora $b\equiv a \ (n)$
>Se $a-b$ è multiplo di $n$ lo è anche $b-a$

>[!done] Proprietà Transitiva
>Se $a \equiv b \ (n)$, $b\equiv c\ (n)$ allora $a \equiv c \ (n)$
>Perchè se $a-b =hn$ e $b-c=kn$
>allora $a-c = (a-b)+(b-c) = (h+k)n$
>

## Funzione o Applicazione
---
>[!info] Definizione
>Siano $A$ e $B$ insiemi non vuoti una **funzione o applicazione** che va d a$A$ a $B$ è una legge che associa ad ogni elemento dell'insieme $A$ uno e un solo elemento dell'insieme $B$

![[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Surriettiva]]

![[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Iniettiva]]

![[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Biunivoca]]

## Insiemi Numerici
![[Insiemi Numerici#Tipologie]]
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