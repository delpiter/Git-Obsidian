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