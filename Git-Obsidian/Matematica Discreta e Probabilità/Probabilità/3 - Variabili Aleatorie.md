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

### Variabili Discrete
>Lanciamo un dado 2 volte

$X=\#$ di volte che esce $6$
- $X$ può assumere i valori: $\{ 0,1,2 \}$

$\mathcal{P}(X=0)=\displaystyle\frac{5}{6}\cdot \frac{5}{6}=\frac{25}{36}$
$\mathcal{P}(X=1)=\displaystyle2\cdot \frac{5}{6}\cdot \frac{1}{6}$
$\mathcal{P}(X=2)=\displaystyle\frac{1}{6} * \frac{1}{6}=\frac{1}{36}$

>[!note] Osservazione
>La somma dei 3 risultati è $1$


#### Densità
>[!info] Definizione
>La ***densità*** di una *variabile aleatoria* **discreta** è una funzione:
>$$\begin{array}\ dx:\mathbb{R}\to[0,1] \\k\mapsto \mathcal{P}(X=k)\end{array}$$

>Dall'esempio di prima

$$
dx(k)=\begin{cases}
\displaystyle{\frac{25}{36}}\quad \text{ se }k=0 \\
\displaystyle{\frac{10}{36}}\quad \text{ se }k=1 \\
\displaystyle{\frac{1}{36}}\quad \text{ se }k=2
\end{cases}
$$

>[!note] Osservazione
>Se $dx$ è la ***densità*** di $X$
><u>Allora</u>
>- $dx(k)\geq 0$
>- $dx(k)>0$ per una quantità discreta di valori $k$
>- $\displaystyle\sum_{k}dx(k)=1$


##### Densità Discreta Astratta
>[!abstract] Definizione
>Una funzione $d:\mathbb{R}\to\mathbb{R}$ si dice ***densità discreta astratta*** se:
>- $dx(k)\geq 0$
>- $dx(k)>0$ per una quantità discreta di valori $k$
>- $\displaystyle\sum_{k}dx(k)=1$

###### Esempio
>Insieme finito
$$
d(k)=\begin{cases}
\displaystyle{\frac{1}{4}}\quad \text{se }k=\{ -1,3 \} \\
\displaystyle{\frac{1}{2}}\quad \text{se } k=10 \\
\ 0 \ \quad \text{altrimenti}
\end{cases}
$$
>Esempio di ***densità discreta astratta***


###### Esempio
>Insieme Numerabile

$$
d(k)=\begin{cases}
2^{-k}\quad \text{ se } k=\{ 1,2,3,\dots \}\\
0 \qquad \text{ altrimenti}
\end{cases}
$$

>[!done] 1\) $d(k)\geq 0$

>[!done] 2\) $d(k)> 0$
>Solo se $k$ è intero positivo

>[!done] 3\) $\frac{1}{2}+\frac{1}{4}+\frac{1}{8}+\dots$
>Serie che converge verso $1$


### Variabili Discrete e Densità Uniforme
>[!info] Definizione
>Dato un insieme $A=\{ a_{1},a_{2},\dots,a_{n} \}\subseteq \mathbb{R}$, consideriamo la funzione:
>$$d(k)=\begin{cases}\displaystyle{\frac{1}{n}}\quad \text{ se } k=a_{1},a_{2},\dots,a_{n} \\\ 0 \quad \ \text{ altrimenti}\end{cases}$$
>Una funzione di ***densità astratta uniforme*** su $A$
>>[!note] Notazione
>>Se $X$ è una variabile aleatoria t.c. $dx=d$
>>Diciamo che $X$ è uniforme su $A$ e scriviamo
>>$$X \sim U(A)$$

##### Esempio
>Consideriamo il lancio di un dado

$X=$ Il *risultato*

$$
dx(k)=\begin{cases}
\frac{1}{6}\quad \text{ se } k=\{ 1,\dots,6 \} \\
\ 0 \quad \text{ altrimenti}
\end{cases}
$$

- $X\sim U(\{ 1,2,3,4,5,6 \})$

#### Variabili e Densità di Bernoulli
>([Bernoulli](https://pixarcars.fandom.com/wiki/Francesco_Bernoulli))

>[!info] Definizione
>Una variabile aleatoria $X$ è di Bernoulli se assume solo valori $0$ e $1$
>$$dx(k)=\begin{cases}p \qquad \quad\text{ se } k=1 \\1-p \quad \ \text{ se } k=0 \\0 \qquad \quad \text{ altrimenti}\end{cases}$$
>>[!Note] Notazione
>>Scriviamo in questo caso:
>>$$X \sim B(1,p)$$

>Se $E$ è un *evento*

La funzione indicatrice di $E$ è:
$$
X_{E}=\begin{cases}
1 \quad \text{se }\ E \ \text{ accade} \\
0 \quad \text{se }\ E \ \text{ non accade}
\end{cases}
$$
- $X_{E}\sim B(1,\mathcal{P}(E))$
##### Esempio
>Consideriamo il lancio di un dado

$$
X=\begin{cases}
1 \quad \text{se il risultato } \geq 5 \\
0 \quad \text{se il risultato } < 5 
\end{cases}
$$
- $\mathcal{P}(X=1)=\displaystyle{\frac{1}{3}}$
- $\mathcal{P}(X=0)=\displaystyle{\frac{2}{3}}$

$$
X\sim B(1,3)
$$

