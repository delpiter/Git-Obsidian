> Siano $A$ e $B \neq \varnothing$  chiamiamo funzione da $A$ a $B$ una legge che ad ogni elemento di $A$ associa uno ed un solo elemento di $B$
 
$$f:A\rightarrow B$$
- Dove $A$ rappresenta il dominio della funzione e $B$ il codominio
$$\forall x \in A, \exists y \in B : y = f(x)$$
## Dominio e Codominio e Immagine
#### Dominio
>L'insieme dei valori possibili che la variabile $x$ può assumere
- L'insieme su cui è definita la funzione.
#### Codominio
>È l'insieme dove sono contenute tutte le immagini della funzione

#### Immagine
>Il sottoinsieme di $y$ costituito dai valori effettivamente assunti dalla funzione $f$ è invece detto immagine
$$f(A)=\{y\in B\;|\;\exists; x\in A:f(x)=y\}$$
---
## Grafico di una Funzione
>Siano $A$ e $B \neq \varnothing$, sia $f: A \rightarrow B$ chiamiamo grafico di $f$, l'insieme 
$$y_f =\{(a,b) \in A\times B \; | b=f(a)\}$$
#### Iniettività e surriettività
###### Surriettività $[f\;su]$
>Diciamo che $f$ è surriettiva se $f(A)=B$
>>Cioè se per ogni elemento del codominio, c'è almeno un elemento del domino associato
$$\forall x \in B, \exists \; x \in A | f(x)=y$$
###### Iniettività $[f\;1-1]$
>Diciamo che $f$ è iniettiva se:
>>Ogni elemento del dominio ha una immagine distinta
$$\forall y \in f(A), \exists! \;x \in A | f(x)=y$$
- Oppure se $f(x_1) = f(x_2) \Rightarrow x_1=x_2$
###### Funzione invertibile
>Diciamo che $f$ è invertibile (Biettiva o Biunivoca) se è sia iniettiva che surriettiva

###### Funzione inversa
> Sia $f:A\rightarrow B$ invertibile chiamiamo funzione inversa di $f$ la funzione
$$f^-1:B\rightarrow A$$
- Definita come segue
	- $\forall y\in B,f^-1(y)$ è l'unica soluzione dell'equazione $f(x)=y$
