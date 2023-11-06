## Estremante Locale
---
>[!info] Definizione
>Sia $I$ intervallo di $\mathbb{R}$, $f:I \to\mathbb{R}$
>Sia $c\in I$
>
>>[!tldr] Minimo
>>Diciamo che $c$ è un punto di minimo locale per $f$ se:
>>$$\exists \delta>0:\forall x \in(c-\delta,c+\delta)\cap I$$
>>E si ha $f(c)\leq f(x)$
>
>>[!tldr] Massimo
>>Diciamo che $c$ è un punto di massimo locale per $f$ se:
>>$$\exists \delta>0:\forall x \in(c-\delta,c+\delta)\cap I$$
>>E si ha $f(c)\geq f(x)$

### Dimostrazione Grafica
![[Pasted Image 202304523.jpg]]

## Teorema di Fermat
---
>[!info] Teorema
>Sia $I$ intervallo di $\mathbb{R}$, $f:I \to\mathbb{R}$
>Sia $c$ [[Definizioni_Analisi#Punto interno in un Intervallo|punto interno]] di $I$
>Supponiamo che $f$ sia derivabile in $c$ e $c$ è [[#Estremante Locale]]
><u>Allora</u>
>$f'(c)=0$

### Dimostrazione
Sia $c$ punto di minimo locale
$$
\exists \delta>0:f(c)\leq f(x) \forall x \in(c-\delta,c+\delta)\cap I
$$
>[!done] Alternativa
>Scegliendo $\delta$ sufficientemente piccolo posso supporre che $(c-\delta,c+\delta)\subset I$ poichè $c$ è un punto interno di $I$

##### Considerando il [[Derivate#Rapporto Incrementale|rapporto incrementale]]:
$$
\displaystyle{\frac{f(x)-f(c)}{x-c}}
$$
###### Abbiamo 2 casi:
- $f(x)-f(c)\geq0$ poichè $c$ è un punto di minimo
- Con $\forall x \in(c,c+\delta)$
	- $x-c\geq 0$
	- Quindi il rapporto incrementale è sempre $\geq 0$
- Con $\forall x \in(c-\delta,c)$
	- $x-c\leq 0$
	- Quindi il rapporto incrementale è sempre $\leq0$

###### Passando al Limite

$\lim\limits_{x\to c^+} \displaystyle{\frac{f(x)-f(c)}{x-c}}\geq0$
e
$\lim\limits_{x\to c^-} \displaystyle{\frac{f(x)-f(c)}{x-c}}\leq0$

E poichè $f$ è derivabile $$f'(c) = \lim\limits_{x\to c} \displaystyle{\frac{f(x)-f(c)}{x-c}}=0$$
- Si può fare un ragionamento analogo anche per $c$ punto di massimo locale
### Esempio di $c$ interno ipotesi necessaria
Prendiamo $f(x)=x$ nell'intervallo $[0,1]$
- In questo caso $0$ è punto di minimo, tra l'altro anche assoluto, ma la sua derivata vale $1$
- Il punto $1$ è un punto di massimo, anche assoluto, ma la sua derivata vale $1$

## Teorema di Rolle
---

>[!info] Teorema
>Sia $f:[a,b]\to\mathbb{R}$, una funzione [[Introduzione Funzioni#Continuità|continua]] in $[a,b]$ e derivabile in $(a,b)$
>Supponiamo che $f(a)=f(b)$
><u>Allora</u>
>$$\exists c\in (a,b):f'(c)=0$$

### Dimostrazione
Dato che $f$ è derivabile su $[a,b]$, per il [[Introduzione Funzioni#Teorema di Weierstruss|teorema di Weierstruss]] esistono $max$ e $min$ di $f$
- Ho due possibilità:
#### $max$ e $min$ negli estremi
Se $max(f)$ e $min(f)$ sono entrambe assunti negli estremi
- Es $f(a)=max(f)$ e $f(b)=min(f)$ si può dedurre che $f$ è costante e dunque
$$
f'(x)=0\ \ \ \ \ \ \forall x\in[a,b]
$$
#### $max$ o $min$ assunti internamente
Se almeno uno, trs $max$ e $min$, è assunto all'interno di $(a,b)$ allora in tale punto $c$ posso applicare il [[#Teorema di Fermat]] e dedurre che:
$$
f'(c)=0
$$
### Visualizzazione Grafica
![[Pasted image 20231106151817.png]]

## Teorema di Lagrange
---
>[!info] Teorema
>Sia $f:[a,b]\to\mathbb{R}$, una funzione [[Introduzione Funzioni#Continuità|continua]] in $[a,b]$ e derivabile in $(a,b)$
><u>Allora</u>
>$$\exists c\in(a,b):f'(c)= \displaystyle{\frac{f(b)-f(a)}{b-a}}$$
>
>>[!done] In breve
>>Esiste un punto nella funzione per cui il coefficiente angolare della retta tangente passante per quel punto è uguale al coefficiente angolare della retta secante passante per i punti $(a,f(a))$ e $(b,f(b))$

### Dimostrazione
Considero la funzione:
$g(x)=f(x)-f(a)- \displaystyle{\frac{f(b)-f(a)}{b-a}}(x-a)$
>[!done] $g(x)$
>$g(x)$ è la differenza fra la funzione originale $f(x)$ e la funzione della retta secante passante per gli estremi

- $g$ è derivabile in $(a,b)$ e [[Introduzione Funzioni#Continuità|continua]] in $[a,b]$ per somma e differenza di funzioni continue e derivabili
Inoltre
- $g(a)=\cancel{ f(a)-f(a) }- \cancel{ \displaystyle{\frac{f(b)-f(a)}{b-a}}(a-a) }=0$
- $g(b)=f(b)-f(a)- \displaystyle{\frac{f(b)-f(a)}{\cancel{ b-a }}}\cancel{ (b-a) }=0$
Adesso è possibile applicare il [[#Teorema di Rolle]] a $g$ e deduco che
$$
\begin{array}
\ \exists c \in(a,b)t.c. \\
g'(c)=0 \Leftrightarrow f'(c)=\displaystyle{\frac{f(b)-f(a)}{b-a}}
\end{array}
$$

### Visualizzazione Grafica
![[Pasted image 20231106151842.png]]

## Teorema test di Monotonia
---
>[!info] Teorema
>Sia $I$ intervallo di $\mathbb{R}$, $f:I\to\mathbb{R}$, derivabile
><u>Allora</u>
>$f \text{ è }\nearrow \text{ in }I\Leftrightarrow f'(x)\geq0 \ \ \forall x\in I$
>$f \text{ è }\searrow \text{ in }I\Leftrightarrow f'(x)\leq0 \ \ \forall x\in I$