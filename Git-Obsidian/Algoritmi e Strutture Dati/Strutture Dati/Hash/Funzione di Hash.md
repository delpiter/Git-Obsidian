## $h(x)$
---
>[!info] Descrizione
>La *funzione di hash* è il gestore della posizione della [[Hash Table]]
>La funzione hash $h$ prende in `input` una ***chiave*** e *restituisce* un valore compreso tra $0$ e $m-1$
>Si utilizza un vettore $T$ di *puntatori* con $m$ posizioni indicizzate
>L'elemento $x$ con chiave $x.key$ viene *memorizzato* in $T$ in posizione $h(x.key)$
![[Screenshot_2024-03-17_164254-removebg-preview.png]]

- Nelle [[Hash Table#Direct Address Table|direct access table]] la funzione di hash è semplicemente la [[Git-Obsidian/Analisi/Funzioni/Introduzione Funzioni#Funzione Identità|funzione identità]]
	- $h(x) = x$

### Collisioni
>[!info] Definizione
>Siano $x$ e $y$ due valori da passare alla funzione *hash* $h$
>$x$ e $y$ generano una ***collisione*** se
>$$x\neq y \text{ e } h(x) = h(y)$$ 

La funzione di hash deve cercare di minimizzare le collisioni

>[!abstract] Obbiettivi contrastanti

La *funzione hash* ha due obbiettivi contrastanti:
1. Comportarsi come una ***funzione casuale***
	- *Minimizza le collisioni*, quando inevitabile, appaiono in maniera *omogenea*
2. Essere ***deterministica***
	- Il processo di **hashing** deve essere *ripetibile*
	- Stesso `input` $\to$ stesso `output`

#### Frequenza delle collisioni
>[!tip] Sia $T$ una tabella di dimensione $m$ e $p$ il numero di elementi da inserire

La *funzione hash* ha $m^p$ diverse possibilità di allocazione dei $p$ elementi
- Con $p=8$ e $m=10$ ci sono $10^8$ possibili allocazioni diverse

Ci sono $\displaystyle{\frac{m!}{(m-p)!}}$ **possibilità** di un *hashing senza collisioni*

La probabilità di collisione *cresce in modo sorprendente*

## Tecniche di Gestione di Collisioni
---
### Chaining
>[!info] Risoluzione di collisioni con "***chaining***"
>Si crea una [[Linked Lists|lista]] per ogni cella della tabella (valori assumibili dalla funzione $h$)
>Si collegano i *record* afferenti a una *stessa cella* nella sua lista
>Le celle della tabella sono le *teste delle liste* (`NULL` se liste vuote)

![[Pasted image 20240317170426.png]]
#### Analisi della Complessità
>[!info] Load Factor
>Il *Load Factor* è una misura di quanto la tabella è piena
>- $n$ Numero di elementi memorizzati nella tabella
>- $m$ Dimensione della tabella
>$$\text{ Load Factor }\to \alpha = \frac{n}{m}$$
>

>[!fail] Caso Pessimo
>>Tutte le $n$ *chiavi* finiscono nella **stessa posizione**
>>- Ricerca: $\Theta(n)$


>[!warning] Caso Medio
>>***Simple Uniform Hashing***
>>La funzione di hash $h$ *suggerisce* una cella del vettore con una ***stessa probabilità*** di un'altra

##### Simple Uniform Hashing
>[!info] Definizione
>Sia $n$ una *funzione hash*
>Diciamo che $h$ è uniforme se per ogni chiave $k$ e per ogni coppia di indici $i,j$ della tabella $T$ vale la relazione:
>$$(\text{Probabilita}[h(k)=i])=(\text{Probabilita}[h(k)=j])$$

>[!tip] $h$ Semplice Uniforme
>Una *funzione hash* si dice ***semplice uniforme*** quando rende **uniforme** il *riempimento* della tabella

###### Complessità SUH
>[!teorema]
>Siano le collisioni ***gestite con chaining***
>Sia la funzione di hash ***Semplice Uniforme***
><u>Allora</u>
>Una ricerca ha [[Complessità di Algoritmi#Analisi di Complessità|costo computazionale]] di $\Theta(1+\alpha)$
>Dove $1$ è il costo della funzione $h$ e $\alpha$ è il ***load factor***

>[!hint] Dimostrazione
>Caso di ricerca ***senza Successo***

Il *Load Factor* $\alpha$ è la lunghezza media di una *catena*
- In una ricerca **senza successo** il numero di *elementi esaminati* è uguale alla ***lunghezza media*** delle catene
$$
\frac{n}{m}=\alpha
$$
Dato che calcolare $h()$ costa $\Theta(1)$

La ricerca costerà
$$
\Theta(1)+\Theta(\alpha) = \Theta(1+\alpha)
$$

>[!hint] Dimostrazione
>Caso di ricerca ***con Successo***

Assumiamo di inserire elementi in *coda alla catena*
- Per ipotesi il numero medio di elementi in una catena dopo $i$ inserimenti è
$$
\frac{i}{m}
$$
L'elemento $i$ verrà inserito *mediamente* nella posizione $1+\displaystyle{\frac{(i-1)}{m}}$ all'interno di una catena

Un elemento generico finirà in media nella posizione data dalla formula:
$$
\frac{1}{n}\sum_{i=1}^n \left( 1+\displaystyle{\frac{(i-1)}{m}} \right)
$$
Scomponiamo la sommatoria:
$$
\begin{array}
\ \underbrace{ \displaystyle\sum_{i=1}^n 1 }_{ n } + \displaystyle\sum_{i=1}^n \frac{i}{m} - \underbrace{ \displaystyle\sum_{i=1}^n \frac{1}{m} }_{ \frac{n}{m} } \\
n+\displaystyle\frac{1}{m}\displaystyle\sum_{i=1}^ni + \frac{n}{m} \\
n+\displaystyle\frac{1}{m}\cdot \displaystyle{\frac{n(n+1)}{2}} + \frac{n}{m} 
\end{array}
$$

Ora torniamo alla funzione originale
$$
\frac{1}{n}\left( n+\displaystyle{\frac{n(n+1)}{2m}}-\frac{n}{m} \right)=
$$
$$
1+\displaystyle{\frac{(n+1)}{2m}}-\displaystyle{\frac{2}{2m}}=
$$
$$
1+\displaystyle{\frac{n-1}{2m}}=
$$
$$
1+\underbrace{ \frac{n}{2m} }_{ \alpha/2 }-\frac{1}{2m}=\Theta(1+\alpha)
$$
>[!done] Conclusione

Supponiamo che $n=O(m)$
- Ovvero che il numero di **elementi** inseriti nella tabella sia *proporzionale alla dimensione* della tabella stessa
$$
\alpha = \frac{n}{m} =\frac{O(m)}{m} = O(1)
$$
In questo caso la ricerca impiega ***tempo costante***!

Se usiamo le [[Linked Lists#Doubly Linked List|doubly linked lists]] per le catene e se inseriamo in testa alle liste i nuovi elementi abbiamo che:
- Ricerca
- Cancellazione
- Inserimento
Fanno in media $O(1)$ operazioni

###### Progettazioni Funzioni Hash
>[!hint] Progettazione
>Siano $Pr(k)=$ Probabilità della chiave $k$
>$S_{j}=\{ k\in U :h(k)=j\}$
>Vogliamo ***uniform hashing*** ovvero:
>$$\sum_{k\in S_{i}}Pr(k)=\frac{1}{m}$$
>Con $m =$ Dimensione della tabella

Se $Pr()$ è sconosciuta:
- Si utilizzano ***algoritmi euristici***
	- Algoritmi che cercano di risolvere il problema al meglio che possono

>[!abstract] Metodo della Divisione
>$$h(k)=k mod(m)$$

>[!abstract] Metodo della Moltiplicazione
>$$h(k)=\lfloor m(kA mod1)\rfloor$$
>Passaggi:
>1. Scegli una costante $A$ con $0<A<1$
>2. Calcola $k\cdot A$
>3. Prendi la parte frazionaria: $k\cdot A-\lfloor k\cdot A\rfloor$
>4. Moltiplica il risultato per $m$
>5. Prendi la parte intera
>La chiave $k$ è mappata in $\lfloor(m\cdot(k\cdot A-\lfloor k\cdot A\rfloor))\rfloor$

Costante $A$ ottimale:
- $(5^{\frac{1}{2}}-1)/2 = 0.618\dots$

### Open Addressing
>[!info] Risoluzione di Collisioni con Open Addressing
>Nell'***open addressing*** la tabella è *dimensionata* in accordo con il numero di dati da inserire
>A contrario del *chaining* è possibile **finire lo spazio** a disposizione
>L'hash function $h$ è più complessa, prende come parametri la *chiave* e il ***numero di collisioni già avvenute***

#### Uniform Hashing
>[!info] Funzione Hash
>Se gestiamo le collisioni con il metodo ***open addressing***
>la funzione hash restituisce una permutazione degli indici $<1,\dots,m>$
>Invece di simple uniform hashing parliamo di **uniform hashing**
>>[!abstract] Concetto
>>Tutte le permutazioni devono apparire con la stessa probabilità

#### Pseudocodici
```pseudo
	\begin{algorithm}
	\caption{Insert}
	\begin{algorithmic}
\Procedure{HashInsert}{$ T,k $}
\State $ i=0 $
\Repeat
	
\State $ j= $\Call{h}{k,i} 
	\If{$ T[j]=null \text{ OR } T[j]='d' $}
  \State $ T[j]=k $
  \Return $ j $
  \Else 
 \State $ i=i+1 $
 \EndIf
\Until{i=m}
\State $ \text{"error hash table overflow"} $	
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

```pseudo
	\begin{algorithm}
	\caption{Search}
	\begin{algorithmic}
\Procedure{HashSearch}{$ T,k $}
\State $ i=0 $
\Repeat
\State $ j= $	\Call{h}{$k,i$}
	\If{$ T[j]=k  $}
	\Return $ j $
	\Else 
 \State $ i=i+1 $
  
 \EndIf
\Until{$T[j]==null \text{ OR } i==m$}
	\Return $ null $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

```pseudo
	\begin{algorithm}
	\caption{Delete}
	\begin{algorithmic}
\Procedure{HashDelete}{$ T,k $}
\State $ i= $ \Call{HashSearch}{T,k}
\If{$ i\neq null  $}
  \State $ T[i]='d' $
 \EndIf
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

#### Linear Probing
