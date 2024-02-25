Ogni problema può essere risolto in **molti modi diversi**
- Ne consegue il fatto che esistono diversi algoritmi di soluzione per uno stesso problema

>[!question] Quale conviene usare??

Esiste un modo per confrontare algoritmi
Necessità:
- Deve essere possibile saperli rappresentare $\to$ **pseudocodice**
- Deve essere possibile saperli confrontare $\to$ **Notazione O grande**
## Pseudocodice
---
Un [[Problemi e Algoritmi#Algoritmo|algoritmo]] è espresso come una sequenza di azioni elementari (*passi*) da eseguire per risolvere il [[Problemi e Algoritmi#Problemi|problema]]

>[!info] Pseudocodice
>I passi di un algoritmo vengono rappresentati con un *linguaggio astratto ed informale*
>- Non richiede *regole sintattiche*, necessarie in un linguaggio di programmazione
>- Utilizza la struttura di un linguaggio di programmazione normale ma è inteso *per la comprensione umana*
>- Il linguaggio è aumentato con passi in *linguaggio naturale*
>- **Non esiste** nessuno **standard**

>[!done] Qualche "regola":

Esistono alcune parole chiavi comuni:
- `do while  ... endDo;`
- `repeat ... until;`
- `if ... endif;`
- `case ... endCase;`
- `return ...;`

Gli ***array*** hanno indici che iniziano da $1$.

I blocchi devono essere sempre ***indentati***
- Racchiusi o fra **parentesi graffe** o fra **parole chiave e terminatore**

Spesso vengono usati anche **verbi della lingua ingelse**

##### Esempio
```pseudo
	\begin{algorithm}
	\caption{Example}
	\begin{algorithmic}
	\Procedure{max}{$ a_{1} ,a_{2},a_{3},...,a_{n} $}
	\State $ max = a_{1} $
	\For{$ i=2 \to n $}
 \If{$ max<a_{i}  $}
 \State $ max=a_{i} $ 
 \EndIf 
 \EndFor
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```
### Sommatorie
Spesso nello pseudocodice si possono usare sommatorie per semplificare la lettura dell'algoritmo.

#### Sommatorie utilizzate
>[!tip] Serie costante

$$
\sum^b_{i=a}1 =\begin{cases}
(b-a+1) \text{ se } b\geq a \\
0 \text{ altrimenti}
\end{cases}
$$
>[!tip] Serie Aritmetica $n\geq0$

$$
\sum^n_{i=0}i = \displaystyle{\frac{n(n+1)}{2}}
$$
>[!tip] Serie Geometrica $n\geq0$ e $x\neq 1$

$$
\sum^n_{i=0} x^i = \displaystyle{\frac{x^{n+1}-1}{x-1}}
$$
- Se $\mid x\mid <1$ allora
$$
\sum^n_{i=0} x^i = \displaystyle{\frac{1}{1-x}}
$$
>[!tip] Serie Armonica $n\geq 1$

$$
\sum^n_{i=1} \frac{1}{i} \approx ln(n)
$$

## Analisi di Complessità
---
Diversi algoritmi possono risolvere uno stesso problema
>[!question] Qual è il miglior modo?

>[!info] Soluzione
>L'***analisi di complessità*** è un metodo formale per prevedere le risorse richieste dall'algoritmo come il ***tempo di esecuzione*** e la ***quantità di memoria*** utilizzata.

### Risorse
Le risorse possono essere diverse: 
- La risorsa principale è il **tempo**
	- Meno tempo un algoritmo ci mette a risolvere il problema, meglio è
- Memoria richiesta
	- Chi utilizza più memoria si trova più facilmente a cercare di utilizzare più memoria di **quanto se ne è a disposizione**
	- Meno se ne usa meglio è.
- Numero di `CPU`
	- È sempre meglio lasciare libera una parte della `CPU`
- Banda passante per la comunicazione
- Energia elettrica consumata

Tempo e Memoria sono le due risorse più sensibili
- Il tempo è la risorsa con la **sensibilità massima**

Le altre risorse variano di sensibilità in base all'impiego del calcolatore
#### Esempio
In un computer utilizzato per *minare criptovalute* la risorsa dell'energia elettrica avrà una sensibilità maggiore rispetto ad un computer utilizzato per altri impieghi.

### Fattori del tempo di `CPU`
>[!example] Ci sono diversi fattori che influiscono sul tempo di `CPU`

>[!tip] Dimensione dell'Input

Più grande è l'input più tempo sarà necessario per eseguire l'algoritmo
- Crescita lineare del **tempo di lettura**

>[!tip] Tempo di Elaborazione

Dipende dall'algoritmo

>[!tip] Velocità di accesso alla Memoria

I dati vengono salvati nella memoria `RAM` più è veloce meno durerà l'esecuzione

>[!tip] Velocità della `CPU`

>[!tip] Numero di processori

>[!tip] Ottimizzazione del [[Definizioni_Architettura#Compilazione|compilatore]]/[[Definizioni_Architettura#Linker|linker]]

#Da_Chiedere Come il compilatore influisce sul tempo di esecuzione

### Tempo di Esecuzione
>[!info] Definizione
>Il tempo di esecuzione di un algoritmo può essere espresso come il **numero di passi necessari** per risolvere il problema

```pseudo
	\begin{algorithm}
	\caption{Example 1}
	\begin{algorithmic}
	\Procedure{p1}{$ a_{1},...,a_{n} $}
\State $ min=a_{1} $
\State $ max = a_{1} $
\For{$ i=2 \to n $}
  \If{$ a_i < min $}
  \State $ min = a_i $
\Elsif{$ a_i > max $} 
 
 \State $ max = a_i $
 \EndIf
 \EndFor
 \State $ m = max - min $
 \Return $ m $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

- La differenza in tempi di esecuzione su due calcolatori diversi ***non deve essere un fattore di miglioramento dell'algoritmo***
L'assegnazione di un valore ad una cella di memoria è ***l'azione più costosa*** in termini di tempo (nell'algoritmo $\text{Example 1}$)
- Contandole si ha una approssimazione del tempo di esecuzione
- Possiamo denotare questo con una funzione $T$, dove $T(n)=3+(n-1)$
	- Dove $n$ è il numero di parametri in input
### Lettura e scrittura
>[!info]
>Leggere e scrivere dati in parti diverse del calcolatore ha delle differenze di tempo molto elevate
>>[!example] In ordine di velocità:
>>1. Registri della `CPU`
>>2. Cache
>>3. `RAM`
>>4. Mass Storage Unit

### O Grande
Concetto simile a quello di [[Resto di Peano|o piccolo]] in matematica
La dimensione del problema per $\text{Example 1}$ è il numero di interi in input
- Una istanza con $100000$ interi è più grande di una con $1000$
- E' ovvio che il tempo di esecuzione cresce con la dimensione dell'istanza

>[!question] Quanto?

Non interessa il numero esatto di istruzioni, si considera solo il **termine dominante**
- Così si ottiene una approssimazione di $T(n)$

Interessa l'andamento della funzione andando verso ***valori sempre più grandi***
- Come per i limiti di funzione, per la complessità di un algoritmo si **seleziona il termine dominante**
- Anche i *coefficienti* diventano non significativi per $n$ molto grandi

L'**ordine di grandezza** di $T(n)$ dipende solo dal termine che cresce di più al crescere di $n$
- Ordine di grandezza si scrive ***O grande***
$f(x) = x^3+6x^2+9x+10$
$$O(f(x)) = O(x^3)$$
Un algoritmo $O(n^3)$ non può essere usato per istanze molto grandi, mentre un algoritmo $O(n)$ è utilizzabile per istanze di dati molto grandi

### Caso ottimo, medio, pessimo

Spesso il tempo di esecuzione dipende dai valori letti in input, ***non dalla dimensione dell'input***.

Istanze **grandi uguali** possono avere tempi di esecuzione **molto diversi**

- Per questi algoritmi dobbiamo definire una caratterizzazione del caso pessimo, caso ottimo, e caso medio

>[!danger] Caso Pessimo
>Il caso pessimo lo si ha per input che ***rendono massimo il tempo di esecuzione***.

>[!done] Caso Ottimo
>Il caso ottimo lo si ha per input che rendono ***minimo il tempo di esecuzione***.

>[!tip] Caso Medio
> Il caso medio lo si ha con riferimento ***all'intero universo di input possibili***, lo si può identificare con **metodi statistici**, spesso complessi.

