## Trasformazione
---
>Sia $(X,Y)$ una [[4 - Variabili Aleatori Multidimensionali|variabile aleatoria bidimensionale]]  

- $Z=X+Y$ è una trasformazione ***somma***

>[!question] Possiamo calcolare $d_{Z}$ in funzione di $d_{X,Y}$

#### Esempio
>Gara di tiro con l'arco a coppie

$A$ e $B$ fanno 3 tiri ciascuno
- $A$ fa centro con probabilità $3 /4$
- $B$ fa centro con probabilità $1 / 2$

$X=\#$ centri di $A$
$Y=\#$ centri di $B$
$Z=\#$ centri totali della squadra

- $X\sim B(3,3 /4)$
- $Y\sim B(3,1 /2)$

> $Z$ assume valori tra $0$ e $6$

- $d_{Z}(0)=\mathcal{P}(Z=0)=\mathcal{P}(X=0,Y=0)=d_{X,Y}(0,0)$
- $d_{Z}(1)=\mathcal{P}(X=0,Y=1)+\mathcal{P}(X=1,Y=0)=d_{X,Y}(0,1)+d_{X,Y}(1,0)$
- $\dots$
- $d_{Z}(4)=d_{X,Y}(1,3)+d_{X,Y}(2,2)+d_{X,Y}(3,1)$


>[!cite] Quindi
>$$d_{Z}(k)=\sum_{\underset{ l+m=k }{ l,m\  t.c. }}d_{X,Y}(l,m)$$

> Se $Z=XY$

>[!note] Allora
>$$d_{Z}(k)=\sum_{\underset{ l\cdot m=k }{ l,m\  t.c. }}d_{X,Y}(l,m)$$

>Se $Z=F(X,Y)$

>[!cite] Allora
>$$d_{Z}(k)=\sum_{\underset{ F(l,m)=k }{ l,m\  t.c. }}d_{X,Y}(l,m)$$

### Caso Speciale
>$Z=F(X,Y)=max(X,Y)$

###### Esempio
>Lanciamo un dado e una moneta

Li lanciamo ripetutamente fino ad ottenere almeno un ***6*** e almeno una ***testa***

- $X=\#$ lanci per ottenere il primo ***6***
- $Y=\#$ lanci per ottenere la prima ***testa***
- $Z=\#$ lanci totali $\implies Z=max(X,Y)$

## Funzione di Ripartizione
---
