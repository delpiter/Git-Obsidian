## Vettori nel Piano e nello Spazio
---
>[!tldr] Vettore
>Un vettore $\vec{V}$ è individuato da $3$ elementi:
>1) La **_Lunghezza_**, rappresentata da un numero $x\in\mathbb{R} : x\geq0$, anche chiamata modulo del vettore
>2) Una _**Direzione**_, rappresentata da una retta o da qualsiasi sua parallela.
>3) Un _**Verso**_

![[Pasted image 20231128163911.png]]
### Rappresentazione Cartesiana
Fissato un sistema di riferimento con origine $o(0,0)$:
- È possibile assegneare ad ogni punto $A=(x,y)$ il vettore $\vec{V}$ che unisce $o$ e $A$ orientato da $o$ ad $A$
![[Pasted image 20231128164523.png]]

#### Vettori Speciali
Esistono per convenzione due vettori "_particolari_":
- Vettori di lunghezza $1$
- Direzione, quella degli assi del piano cartesiano
- Verso, "verso" i numeri $>0$
![[Pasted image 20231128165050.png]]

- Chiamati **versori**, sempre per convenzione denominati come $i$ e $j$
### Somma tra Vettori
>[!info] Definizione
>Dati due vettori $\vec{V} = \vec{oA}$ e $\vec{W} = \vec{oB}$
>La somma fra di essi si definisce in questo modo:
>Si applica ad $A$ il vettore $W$, cioè scrivo $W=\vec{AC}$
><u>Allora</u>
>Ottengo un nuovo vettore: $\vec{V}+\vec{W} = \vec{oC}$

![[Pasted image 20231128170345.png]]

### Vettore inverso
>[!info] Definizione
>Sia $\vec{V}$ un vettore di lunghezza $x$ e direzione di equazione $ax +c$:
>Il vettore inverso sarà un vettore di ***lunghezza e direzione uguale***, ma con il verso invertito.

![[Pasted image 20231128170944.png]]

### Prodotto di Vettore per uno Scalare
Considerando uno "scalare" come un qualsiasi numero $t\in\mathbb{R}$
>[!info] Definizione
>Sia $V$ un vettore del piano $(V\in\mathbb{R}^2)$, sia $t\in\mathbb{R}$
>Definiamo il vettore $tV$ come il vettore $W$:
>1) $|W| = |t|\cdot|V|$
>2) Direzione di $W$ uguale alla direzione di $V$
>3) Verso di $W=\begin{cases}\text{ verso di } V \text{ se }t>0 \\\text{ verso di } -V \text{ se }t<0\end{cases}$


## Vettori in $\mathbb{R}^3$
---
>[!tldr] Vettore
>La definizione di vettore in $\mathbb{R}^3$ è uguale al vettore in $\mathbb{R}^2$:
>1) La **_Lunghezza_**, rappresentata da un numero $x\in\mathbb{R} : x\geq0$, anche chiamata modulo del vettore
>2) Una _**Direzione**_, rappresentata da una retta o da qualsiasi sua parallela.
>3) Un _**Verso**_
>>[!done] Osservazione
>>Posso identificare un punto $P\in\mathbb{R}^3 = (x,y,z)$ con il vettore che unsice $o$ a $P$ orientato da $o$ a $P$

![[Pasted image 20231129165951.png]]
- In $\mathbb{R}^3$ si aggiunge un ***versore***, denominato $k$
	- $i=(1,0,0),j=(0,1,0),k=(0,0,1)$
	- Di conseguenza un vettore si può rappresentare come:
		- $V=(x,y,z)=ix+jy+kz$
### Modulo, Somma e Moltiplicazione per Scalare
Le operazioni sono analoghe per qualsiasi numero di dimensioni che prendiamo
#### Modulo
- Si applica due volte il teorema di Pitagora
$$
|V|=\sqrt{ x_{p}^2+y^2_{p}+z^2_{p} }
$$
![[Pasted image 20231129170609.png]]
#### Somma di Vettori e Prodotto Scalara
- Analoghi ad $\mathbb{R}^2$

### Prodotto Scalare fra Vettori
>[!info] Definizione
>Definiamo il prodotto scalare tr $V$ e $W$ come:
>$$V\cdot W = |V| |W| cos(\alpha)$$
>Dove $\alpha$ è l'angolo tra $V$ e $W$ compreso tra $0$ e $\pi$


### Prodotto Scalare in Coordinate
#### $\mathbb{R}^2$
- Analogo in $\mathbb{R}^3$
>[!info] Definizione
>Sia $V=(x_{1},y_{1})=x_{1}i+y_{1}j$
>Sia $W=(x_{2},y_{2})=x_{2}i+y_{2}j$
>$$\begin{array}
,V\cdot W = (x_{1}i+y_{1}j)\cdot(x_{2}i+y_{2}j)= \\
=x_{1}i\cdot x_{2}i + \cancel{ x_{1}i\cdot y_{2}j } +\cancel{ y_{1}j\cdot x_{1}i  }+y_{1}j\cdot y_{2}j = \\
=x_{1}\cdot x_{2} +y_{1} \cdot y_{2}
\end{array}
>$$

## Rette e Piani in $\mathbb{R}^3$
---
Una retta in $\mathbb{R}^3$ può essere rappresentata in $3$ modi:
>[!info] Rappresentazione
>Una retta in $\mathbb{R}^3$ è individuata da:
>1) Un punto e una direzione
>2) Da due Punti
>3) Da due Piani, non paralleli

### 1.
- Sia $P_{0}=(x_{0},y_{0},z_{0})$ e sia $V=(a,b,c)\neq 0$
>[!done] In breve
>Un qualsiasi punto $P$ appartenente alla retta $r$ passante per $P_{0}$ e di direzione $V$
>È della forma
>$$P = P_{0}+tV\,\,\, , t\in\mathbb{R}$$

![[Pasted image 20231129175601.png]]
- Il generico punto $P=(x,y,z)$ deve soddisfare le seguenti condizioni
$$
\begin{cases}
x=x_{p0}+ta \\
y=y_{p0}+tb \\
z=z_{p0}+tc
\end{cases}
$$
- Chiamate equazioni Parametriche di una retta in $\mathbb{R}$
	- Sono vere se $a,b,c\neq 0$
	- Es con una coordinata che si annulla
$$
\begin{cases}
x=x_{p0} \\
y=y_{p0}+tb \\
z=z_{p0}+tc
\end{cases}
$$
- Da qui possiamo ricavare l'Equazione cartesiana della retta
$$
\begin{cases}
\displaystyle{\frac{x-x_{0}}{a}} = \displaystyle{\frac{y-y_{0}}{b}} \\
\displaystyle{\frac{y-y_{0}}{b}} = \displaystyle{\frac{z-z_{0}}{c}}
\end{cases}
$$
### 2.
Dati due punti $P_{0}(x_{0},y_{0},z_{0})$ e $P_{1}(x_{1},y_{1},z_{1})$
>[!done] In Breve
>La retta passante per $P_{0}$ e $P_{1}$ non è altro che la retta passante per $P_{0}$ con direzione $V=P_{1}-P_{0}$

![[Pasted image 20231129180244.png]]

## Piano in $\mathbb{R}^3$
Un piano in $\mathbb{R}^3$ può essere rappresentato in $3$ modi:
>[!info] Rappresentazione
>Un piano in $\mathbb{R}^3$ è individuato da:
>1) Un punto e un vettore ortogonale al piano
>2) Tre punti
>3) Due rette non [[Definizioni_Analisi#Rette Sghembe|sghembe]]

