## Valore Atteso di una Variabile Aleatoria Discreta
---
>[!def] Definizione
>Se $X$ è [[3 - Variabili Aleatorie#Variabili Aleatorie Discrete|variabile aleatoria discreta]]:
>$$E[X]=\sum_{k}k\cdot d_{X}(k)$$

>Esempio

$X\sim B\left( 2, \displaystyle{\frac{2}{3}} \right)$

- $E[X]=\sum_{k}k\cdot d_{X}(k)$

>$d_{X}(k)=\displaystyle\binom{2}{k}\left( \frac{2}{3} \right)^k\left( \frac{1}{3} \right)^{2-k}$

- $E[X]=\displaystyle\underbrace{ 1\cdot 2\cdot \frac{2}{3 } \cdot \frac{1}{3} }_{ k=1 }+\underbrace{ 2\cdot 1\cdot\left( \frac{2}{3} \right)^2\cdot\left( \frac{1}{3} \right)^0 }_{ k=2 }= \frac{4}{3}$

>[!cite] In Generale
>Se $X\sim B(n,p)$
>$$E[X]=n\cdot p$$


### Proprietà del Valore Atteso
>Problema principale:
>- Studiare $E[X+Y]$

>[!abstract] Proprietà
>Siano $X$ e $Y$ sue variabili e $Z=F(X,Y)$
><u>Allora</u>
>$$E[Z]=\sum_{h,k}F(h,k)\cdot d_{x,y}(h,k)$$

##### Corollario
>[!hint] Se $X$ e $Y$ sono ***variabili aleatorie discrete***
>$$E[X+Y]=E[X]+E[Y]$$

###### Dimostrazione
>Per la proprietà appena enunciata:

$$
\begin{array}
\ \displaystyle E[X+Y]=\sum_{h,k}(h+k)d_{X,Y}(h,k) \\
=\displaystyle\sum_{h,k}h\cdot d_{X,Y}(h,k)+\sum_{h,k}k\cdot d_{X,Y}(h,k)= \\
=\displaystyle\sum_{h}h\underbrace{ \sum_{k}d_{X,Y}(h,k) }_{ \text{ densità marginale}}+\sum_{k}k\sum_{h}d_{X,Y}(h,k)= \\
=\displaystyle\sum_{h}h\cdot d_{X}(h)+\sum_{k}k\cdot d_{Y}(k)= E[X]+E[Y]
\end{array}
$$

#### Valore atteso di una Variabile Binomiale
>Calcoliamo, ora, il ***valore atteso*** di $X\sim B(n,p)$: [[3 - Variabili Aleatorie#Variabili Binomiali|variabile binomiale]]

Utilizzando la definizione *avremmo*:
- $E[X]=\displaystyle\sum_{k=0}^nk\binom{n}{k}p^k(1-p)^{n-k}$

>[!fail] Calcolo inutilmente complicato

>[!hint] Osservazione
>$X=X_{1}+X_{2}+\dots+X_{n}$
>Dove $X_{i}$ è:
>- $=1$ se l'$i$-esimo tentativo da ***successo***
>- $=0$ se l'$i$-esimo tentativo da ***insuccesso***
>
>>[!done] $X\sim B(1,p)\quad \forall i=1,\dots n$
>>$$E[X]=E[X_{1}+X_{2}+\dots+X_{n}]=E[X_{1}]+\dots+E[X_{n}]=p+p+\dots+p = np$$

#### Valore Atteso di Variabili Ipergeometriche
>Calcoliamo, ora, il ***valore atteso*** di $X\sim H(b,r;n)$: [[3 - Variabili Aleatorie#Schema Successo-Insuccesso senza Rimpiazzo|variabile Ipergeometrica]]

$$
E[X]=\sum_{k=0}^n k \displaystyle{\frac{\binom{b}{k}\binom{r}{n-k}}{\binom{b+r}{n}}}
$$

>[!fail] Calcolo inutilmente complicato

>[!hint] Osservazione
>$X=X_{1}+X_{2}+\dots+X_{n}$
>Dove $X_{i}$ è:
>- $=1$ se l'$i$-esimo tentativo da ***successo***
>- $=0$ se l'$i$-esimo tentativo da ***insuccesso***
>
>>[!done] $X\sim B\left( 1, \displaystyle{\frac{b}{b+r}} \right)\quad \forall i=1,\dots n$
>>$$E[X]=E[X_{1}+X_{2}+\dots+X_{n}]=E[X_{1}]+\dots+E[X_{n}]=$$
>>$$=\displaystyle{\frac{b}{b+r}}+\dots+\displaystyle{\frac{b}{b+r}} = \displaystyle{\frac{nb}{b+r}}$$

##### Esercizio
>$10$ amici, $6$ vaschette di gelato

- $3$ gusti scelti con probabilità: $\displaystyle{\frac{2}{9}}$
- $3$ gusti scelti con probabilità: $\displaystyle{\frac{1}{9}}$

$$
X_{i}=\begin{cases}
1 \quad \text{se il gusto } i
 \text{ è stato scelto da qualcuno} \\
0 \quad \text{se il gusto } i
 \text{ è stato scelto da nessuno}
\end{cases}
$$
$i=1,2,3,4,5,6$

>[!question] Domande
>1. Densità delle $X_{i}$
>2. Le $X_{i}$ sono variabili indipendenti?
>3. Quante vaschette mi devo aspettare di aprire?

>2.

Le variabili $X_{i}$ sono ***indipendenti***:
- Se *nessuno* sceglie la prima scatola, è *più probabile* che le altre vengano scelte

>1. 

$X_{i}\sim B(1,p)$
- $\mathcal{P}(X_{1}=1)=1-\mathcal{P}(X_{1}=0)=1-\left( \frac{7}{9} \right)^{10}=1-0.08=0.92$
- $\mathcal{P}(X_{4}=1)=1-\mathcal{P}(X_{4}=0)=1-\left( \frac{8}{9} \right)^{10}=1-0.31=0.69$


>3. Alternativa:

>[!question] Qual è il valore atteso del numero di vaschette da aprire?

$X=\#$ vaschette da aprire

- $X=X_{1}+X_{2}+\dots+X_{6}$

>[!done] $E[X]=E[X_{1}]+\dots+E[X_{6}]=3\cdot0.92+3\cdot 0.69=4.83$