>[!info] Concetto
>Le [[3 - Variabili Aleatorie|Variabili Aleatorie]] ***Continue*** assumono valori *reali* e non semplicemente *interi* ( o *numerabili*)
>Tipicamente si usano in ***caso di misurazioni***
>>[!example] Esempi
>>Peso, Lunghezza, Tempo, Soldi, etc...

#### Esempi
>Persona a dieta per $8$ settimane

$X=$ Peso alla fine della dieta

>Bambino nato oggi

$Y=$ Altezza in un anno

>Alla fermate del Bus

$T=$ Tempo di attesa

>Investiamo $100$€ in azioni

$Z=$ Valore tra un anno

## Funzione di Ripartizione
---
>Riprendiamo il concetto di [[5 - Trasformazioni di Variabili Aleatorie#Caso Speciale|Funzione di Ripartizione]] fatto in *precedenza*

>[!def] Definizione
>Sia $X$ una [[3 - Variabili Aleatorie|Variabile Aleatoria]] qualunque
>$$\begin{array}\ F_{X}:\mathbb{R}\to[0,1] \\F_{X}(t)=\mathcal{P}(X\leq t)\end{array}$$

#### Esempio Discreto
>$\displaystyle X\sim B\left( 2, \frac{1}{2} \right)$

- $\displaystyle\mathcal{P}(X=0)=\frac{1}{4}\quad \mathcal{P}(X=1)=\frac{1}{2}\quad \mathcal{P}(X=2)=\frac{1}{4}$
>[!question] Chi è la funzione di ripartizione?

![[TMP.png]]

- $F_{X}(1.1)=\mathcal{P}(X\geq 1.1)=\mathcal{P}(X=0)+\mathcal{P}(X= 1)=\displaystyle \frac{1}{4}+\frac{1}{2} = \frac{3}{4}$

## Variabile Aleatoria Continua
---
>[!def] Definizione
>Una [[3 - Variabili Aleatorie|Variabile Aleatoria]] $X$ si dice ***Continua*** se $F_{X}(t)$ è *continua*

![[TMP2.png]]

"*i prossimi calcoli non riflettono l'immagine*"

- $\mathcal{P}(X\leq -1)=F_{X}(-1) = 0$
- $\mathcal{P}\left( X> \frac{3}{2} \right)=1-\mathcal{P}\left( X\leq \frac{3}{2} \right)=1-F_{X}\left( \frac{3}{2} \right)=1-\frac{3}{4}=\frac{1}{4}$
- $\mathcal{P}(X\leq 3)=F_{X}(3)=1$
- $\mathcal{P}(X\leq1)=F_{X}(1)=\frac{1}{2}$

>Caso Speciale

>[!question] $\mathcal{P}(X=1)$ ?

$$
\mathcal{P}(X=1)\leq \mathcal{P}\left( 1-\frac{1}{n}<X\leq1 \right)=\mathcal{P}(X< 1)-\mathcal{P}\left( X\leq 1- \frac{1}{n} \right)=
$$
- Per $n \longrightarrow \infty$
$$
= F_{X}(1)-F_{X}\underbrace{ \left( 1- \frac{1}{n} \right) }_{ \to 1 } = 0
$$
>[!caution] Questo ragionamento vale più in generale
>Se $X$ è una ***variabile aleatoria continua***
><u> Allora</u>
>$$\mathcal{P}(X=t)=0\quad \forall t$$

>[!hint] Osservazione
>Siccome $\mathcal{P}(X=t)=0$
><u>Allora</u>
>- $\mathcal{P}(X\leq t)=\mathcal{P}(X< t)$
>- $\mathcal{P}(X\geq t)=\mathcal{P}(X> t)$

>Quello che avrà più interesse chiedersi è piuttosto:

>[!tldr] $\mathcal{P}(a<X<b)$ per opportuni $a$ e $b$
>Oppure:
>- $\mathcal{P}(X> a)$
>- $\mathcal{P}(X< b)$

$\mathcal{P}(a<X<b)=F_{X}(b)-F_{X}(a)$

## Densità Continua
---
>[!def] Definizione
>La ***densità continua*** di una *variabile aleatoria continua* $X$ è una funzione $f_{X}:\mathbb{R}\to\mathbb{R}$ **tale che**
>$$\forall a<b \quad \mathcal{P}(a<X<b)=\int_{a}^b f_{X}(s)\, ds $$


#### Esempio
> #to_modify *inserisci funzione tutta a 0 tranne tra 0 e 1 che vale 1*

$\displaystyle\mathcal{P}\left( \frac{1}{3}<X<1 \right)=\int_{1}^{1/3} f_{X}(s)\, ds=\frac{2}{3}$
$\displaystyle\mathcal{P}\left( \frac{1}{2}<X<2 \right)=\int_{1}^{1/2} f_{X}(s)\, ds+\underbrace{ \int_{2}^{1} f_{X}(s) }_{ 0 }\, ds=\frac{1}{2}$


### Funzione di Ripartizione e Densità Astratte 
>[!def] Definizione
>Una $f:\mathbb{R}\to\mathbb{R}$ è una ***funzione di ripartizione astratta*** se:
>1. $\lim\limits_{t\to -\infty}f(t)=0\quad \lim\limits_{t\to \infty}f(t)=1$
>2. $f(t)$ ***deve*** essere continua
>3. $f(t)$ è ***debolmente crescente***

>[!tl;dr] Definizione
>Una $f:\mathbb{R}\to\mathbb{R}$ è una ***densità continua astratta*** se:
>1. $f(s)\geq 0\quad \forall s$
>2. $\displaystyle \int_{+\infty}^{-\infty}f(s)  \, ds=1$
>
>>[!warning] Attenzione
>>La densità ***non*** è necessariamente una *funzione continua*