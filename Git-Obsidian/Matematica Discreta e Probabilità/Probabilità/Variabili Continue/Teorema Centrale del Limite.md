>Sia $X\sim U([-1,1])$

![[TeoremaCentrale1.png]]

Il "***centro***" della funzione è composto da *un segmento di grado* $0$

>Siano $X_{1},X_{2}\sim U([-1,1])$ ***indipendenti***

>[!question] $X_{1}+X_{2}$ ?

Come già detto prima, ***non*** abbiamo strumenti adatti per fare la *somma di due variabili continue*
- Ma ci possiamo immaginare il *grafico*

>[!caution] Grafico
>Sappiamo che assumerà valori compresi tra $-2$ e $2$
>Sappiamo, inoltre che sarà *più probabile* che assumerà valori vicini allo $0$

![[TeoremaCentrale2.png]]

Funzione composta da $2$ *segmenti di grado* $1$

>Siano $X_{1},X_{2},X_{3}\sim U([-1,1])$ ***indipendenti***

>[!question] $X_{1}+X_{2}+X_{3}$ ?

>[!caution] Grafico
>Sappiamo che assumerà valori compresi tra $-3$ e $3$
>Sarà formata da $3$ *segmenti di grado* $2$
>- $[-3,-1],\quad [-1,1]\quad [1,3]$

>[!hint] Osservazione
>La ***densità*** della somma $X_{1}+\dots+X_{n}$ di $n$ variabili $U([-1,1])$ è *ben approssimata* dalla [[12 - Variabile Normale o Gaussiana|Densità Normale]] $N(\mu,\sigma^2)$, dove:
>- $\mu=E[X_{1}+\dots+X_{n}]=0$
>- $\sigma^2=Var(X_{1}+\dots+X_{n})=n\cdot Var(X_{1})=n\cdot \frac{2^2}{12}=\frac{n}{3}$
>
>>[!done] $X_{1}+X_{2}+\dots+X_{n}\sim N\left( 0, \frac{n}{3} \right)$

##### Esempio
>Dati dieci numeri casuali compresi tra $-1$ e $1$

>[!question] Qual è la probabilità che la somma dei dieci numeri sia $>7$ ?

$\mathcal{P}(X_{1}+\dots+X_{n}>7)$

Come abbiamo appena visto:
- $\underbrace{ X_{1}+\dots+X_{n} }_{ \zeta }\sim N\left( 0, \frac{10}{3} \right)$
$\mathcal{P}(\zeta>7)=\mathcal{P}\left( \zeta_{0}> \displaystyle\frac{7}{\sqrt{ \frac{10}{3} }} \right)=\mathcal{P}(\zeta_{0}>3.85)\simeq 0$

### Generalizzazione
>[!abstract] Sia $X$ qualunque
>$X_{1},X_{2}$ con la ***stessa densità*** e ***indipendenti***
>La *densità* di $X_{1}+X_{2}$ viene "*smussata*" dalle compensazioni
>
>>[!note] Osservazione
>>Più è *regolare* la ***densità*** meno variabili sono necessarie per avere una ***buona approssimazione***
>

## Teorema Centrale del Limite
---
>[!def] Definizione
>Siano $X_{1},\dots,X_{n}$ [[3 - Variabili Aleatorie|Variabili aleatorie]] ($n\geq20$) *indipendenti*, aventi tutte la ***stessa densità***
>Sia $\mu=E[X_{1}]$ e $\sigma^2=Var(X_{1})$
><u>Allora</u>
>$$X_{1}+X_{2}+\dots+X_{n}\sim N(n\mu,n\sigma^2)$$
>>[!done] Con "***Buona Approssimazione***"

#### Esempio
>Un componente elettronico ha un tempo di vita [[11 - Variabili Esponenziali|esponenziale]] di media $10$ giorni

Ne abbiamo $40$

>[!question] Qual è la probabilità che bastino per un anno?

- $X_{1},X_{2},\dots,X_{40}$: *Tempi di vita* dei componenti

$X_{i}\sim Exp\left( \frac{1}{10} \right)$ e $X_{i}$ sono tutte *indipendenti*

$$
\zeta = X_{1}+X_{2}+\dots+X_{40}\sim N(40\cdot10, 40\cdot 100)
$$
$\mathcal{P}(\zeta>365)=\mathcal{P}\left( \zeta_{0}> \displaystyle{\frac{365-400}{\sqrt{ 4000 }}} \right)=\mathcal{P}(\zeta_{0}>-0.55)=\Phi(0.55)=0.7088$

##### Con Variabili Discrete
>[!question] Il teorema vale anche per le variabili discrete?

>[!done] Si
>Ma bisogna applicare qualche trucchetto per ***trasformare*** la densità *discreta* in densità *continua*

>Sia $X$ una variabile con la seguente densità:

$$
d_{X}(k)=\begin{cases}
\displaystyle\frac{1}{2} \quad \text{se }k=0 \\
\displaystyle\frac{1}{3} \quad \text{se }k=1 \\
\displaystyle\frac{1}{6} \quad \text{se }k=2 \\
0 \quad \text{ altrimenti}
\end{cases}
$$
>Dobbiamo "*estendere*" la densità in modo che risulti come continua

![[TeoremaCentraleDiscreto.png]]

La nuova densità "*estende*" ogni punto di $d_{X}$, tenendolo come centro.

>Consideriamo ora $30$ variabili $X_{1},X_{2},\dots,X_{30}$ aventi la densità appena descritta

$\mathcal{P}(X_{1}+\dots+X_{30}\geq 15)=\mathcal{P}(X_{1}+\dots+X_{30}\geq 14.5)$

- $E[X_{1}]=\frac{1}{3}+2\cdot \frac{1}{6}=\frac{2}{3}$
- $E[X_{1}^2]=1\cdot \frac{1}{3} + 4\cdot \frac{1}{6}=1$
- $Var(X_{1})= 1-\frac{4}{9}= \frac{5}{9}$

$$
\zeta=X_{1}+\dots+X_{30}\sim N\left( 20,30\cdot \frac{5}{9} \right)
$$
$\mathcal{P}(\zeta\geq 14.5) = \mathcal{P}\left( \zeta_{0}> \displaystyle{\frac{14.5-20}{\sqrt{ \frac{50}{3} }}} \right)=\Phi(1.35)=0.9115$

>[!hint] Osservazione
>$\mathcal{P}(X_{1}+\dots+X_{30}=15)=\mathcal{P}(14.5<\zeta<15.5)$

#### Eserczio
>$55$% di voti ad un partito

Scelti 100 votanti a caso

>[!question] Qual è la probabilità che almeno la metà abbia votato quel partito?

$$
X_{i}=\begin{cases}
1 \quad \text{se } i \text{ ha votato il partito} \\
0 \quad \text{altrimenti}
\end{cases}
$$
- $X_{i}\sim B(1,0.55)$

$$
\mathcal{P}(X_{1}+\dots+x_{100}\geq 50)
$$

>[!hint] Osservazione
>$X_{1}+\dots+X_{100}\sim B(100, 0.55)$
>
>Si ***potrebbe*** calcolare come una [[3 - Variabili Aleatorie#Variabili Binomiali|variabile binomiale]] ma verrebbe un calcolo *inutilmente complesso*

>Approssimiamo con il ***teorema centrale del limite***

$$
X_{1}+\dots+X_{100}\sim N(55,100\cdot 0.55 \cdot0.45)
$$

- $\mathcal{P}(X_{1}+\dots+x_{100}\geq 50)=\mathcal{P}(\zeta>49)$
