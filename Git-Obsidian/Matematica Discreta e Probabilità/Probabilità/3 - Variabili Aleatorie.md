>[!info] Definizioni
>>[!example] Non Formale
>>Una *variabile aleatoria* è una quantità che dipende dal risultato del [[1 - Spazi di Probabilità#Fenomeni Aleatori|fenomeno aleatorio]]
>>Cioè, è una funzione $X:\Omega\to\mathbb{R}$
>
>>[!note] Formale
>>Una *variabile aleatoria* è una funzione $X:\Omega\to\mathbb{R}$ t.c.
>>$\forall a \in\mathbb{R}$
>>$\{ r\in\Omega:X(r)\leq a \}$ è un [[1 - Spazi di Probabilità#Evento|evento]]

#### Esempio 1
>Consideriamo il lancio di una dado 6 volte

- $X=\#$ di volte in cui esce $6$
- $Y=\#$ di volte in cui otteniamo un risultato $>$ del precedente

Se i risultati sono:
- $2\quad6\quad 3 \quad6\quad 4\quad 5$

- $X=2$
- $Y=3$

#### Esempio 2
>Sia $\Omega=\mathbb{Z}$
>Con *eventi* $=\{ \varnothing,\ \mathbb{Z},\ ,2\mathbb{Z},\ 2\mathbb{Z}+1 \}$

>[!question] $X(n)=n$ e $Y(n)=(-1)^n$ sono variabili aleatorie?

>Vediamo $X$

Scelgo $a=0$
- $\{ r\in\mathbb{R}:X(r)\leq 0 \}=\{ n\in\mathbb{Z}:n\leq0 \}=\mathbb{Z}_{\geq0}$

>[!fail] Conlcusione
>$\mathbb{Z}_{\geq 0}$ non è un *evento*, quindi $X$ non è una variabile aleatoria

>Vediamo $Y$

Scelgo $a=0$
- $\{ r\in\mathbb{R}:X(r)\leq 0 \}=\{ n\in\mathbb{Z}:(-1)^n\leq0 \}=2\mathbb{Z}+1$

Scelgo $a\geq 1$
- $\{ n\in\mathbb{Z}:(-1)^n\leq a \}=\mathbb{Z}$

Scelgo $-1 \leq a <1$
- $\{ n\in\mathbb{Z}:(-1)^n\leq a \}=2\mathbb{Z}+1$

Scelgo $a< -1$
- $\{ n\in\mathbb{Z}:(-1)^n\leq a \}=\varnothing$

>[!done] Conclusione
>$\forall a$ vale la condizione, $Y$ è una variabile aleatoria


### Abbreviazione
>Sia $X$ una *variabile aleatoria*

>[!note] $\forall t\in \mathbb{R}$
>$$\{ r\in\mathbb{R}:X(r)\leq t \}=\{ X\leq t \}$$

- Posso calcolare $\mathcal{P}(X\leq t)$ poiché è un *evento*

>[!example] $F_{X}(t)=\mathcal{P}(X\leq t)$
>È una funzione  $\mathbb{R}\to[0,1]$ che chiamiamo funzione di ripartizione

#### Versioni Equivalenti

>[!question] Sappiamo che $X\leq t$ è un evento $\forall t$, anche $X> t$ è un evento?

$X>t$
- È un *evento* perché è il **complementare** di $X\leq t$

$X<t$
- È un *evento* perché è **unione** di eventi
	- $X<t=\bigcup\limits_{n>0}X\leq t-\displaystyle\frac{1}{n}$

$X\geq t$
- È un *evento* perché è **complementare** del precedente

$X=t$
- È un *evento* perché è **intersezione** di eventi: "$X\geq t\cap X\leq t$"

$X\neq t$
- È un *evento* perché è **complementare** del precedente

>[!done] Conclusione 
>È Sempre *evento*


## Variabili Aleatorie Discrete
---
>[!info] Definizione
>Una *variabile aleatoria* si dice ***discreta*** se assume una quantità di valori *finita* o *numerabile*

#### Esempio
>Compriamo uno smartphone e lo usiamo finché si rompe

$X=$ Tempo trascorso
- **Non discreto**

$Y=$ Numero di messaggi inviati
- *Numerabile* e quindi *discreto*

$Z$:
- $Z=1$ se sono state effettuate almeno $5$ chiamate al giorno
- $Z=0$ altrimenti
- *Numerabile* e quindi *discreto*

