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
