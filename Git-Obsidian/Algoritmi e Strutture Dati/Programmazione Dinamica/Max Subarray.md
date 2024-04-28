>[!info] Problema
>>[!caution] Input
>>Vettore $A[1,\dots,n]$ di $n$ valori reali arbitrari
>
>>[!done] Output
>>Individuare un ***sotto vettore di elementi contigui*** non vuoto di $A$ tale che la somma degli elementi sia ***massima***


>[!question] Quanti sono i sotto vettori di $A$?

- $1$ *sottovettore* di lunghezza $n$
- $2$ *sottovettori* di lunghezza $n-1$
- $3$ *sottovettori* di lunghezza $n-2$
- $\dots$
- $k$ *sottovettori* di lunghezza $n-k+1$
- $\dots$
- $n$ *sottovettori* di lunghezza $1$

>[!done] Risposta: $n(n-1) /2$

### Soluzione Forza Bruta
```pseudo
	\begin{algorithm}
	\caption{Max Subarray}
	\begin{algorithmic}
\Procedure{MaxSum}{$ A[1,\dots,n] $}
\State $ smax=A[1] $
\For{$ i=1 \to n $}
\Comment{For each possible Start} 
 \For{$ j=i \to n $}
  \Comment{For each possible End}
  \State $ s=0 $
  \For{$ k=i \to j $}
  \State $ s=s+A[k] $
  \Comment{Calculate the Sum of Each subvector}
 \EndFor
 \If{$ s>smax  $}
  \State $ smax = s $
 \EndIf
 \EndFor
 \EndFor
 \Return $ smax $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

>[!caution] Complessità

$$
\Theta(n^3)
$$
### Soluzione più Efficiente
```pseudo
	\begin{algorithm}
	\caption{Max Subarray}
	\begin{algorithmic}
\Procedure{MaxSum}{$ A[1,\dots,n] $}
\State $ smax=A[1] $
\For{$ i=1 \to n $}
  \Comment{For each possible Start}
 \For{$ j=i \to n$}
  \Comment{Sum to every possible End}
  \State $ s=s+A[j] $
  \If{$ s>smax  $}
\State $ smax=s $  
 \EndIf
 \EndFor
 \EndFor
 \Return $ smax $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

>[!caution] Complessità

$$
\Theta(n^2)
$$

### Soluzione con Programmazione Dinamica
>*Il problema si può risolvere con un algoritmo di [[Algoritmi di Programmazione Dinamica#Programmazione Dinamica|programmazione dinamica]]*

Sia $P(i)$ il problema che consiste nel determinare il ***valore massimo della somma*** degli elementi dei ***sottovettori non vuoti*** del vettore $A[1,\dots,i]$ che hanno $A[i]$ come *ultimo elemento*

>Sia $S[i]$ il valore della soluzione di $P(i)$

- $S[i]$ è la massima somma degli elementi dei sottovettori di $A[1,\dots,i]$ che hanno $A[i]$ come ***ultimo elemento***
>[!done] La soluzione $S^*$ al problema di partenza può essere espressa come:

$$
S^* =max_{i\leq i\leq n}(S[i])
$$
#### Procedimento
$P(1)$ ammette una unica soluzione:
- $S[1]=A[1]$

>[!abstract] Consideriamo il generico problema $P(i), i>1$

Supponiamo di avere già risolto il problema $P(i-1)$, e quindi conoscere $S[i-1]$
- Se $S[i-1]+A[i]\geq A[i]$ <u>Allora</u> $S[i]=S[i-1]+A[i]$
- Se $S[i-1]+A[i]< A[i]$ <u>Allora</u> $S[i]=A[i]$

#### Soluzione
>[!tldr] Idea
>>[!caution] Inizializzazione
>>$$S[1]=A[1]$$
>
>>[!example] Espansione
>>Due Casi:
>>1. Inizio un nuovo ***max-subarray*** in $i$
>>$$S[i]=A[i]$$
>>2. Continuo il ***max-subarray*** che finisce in $i-1$
>>$$S[i]=S[i-1]+A[i]$$
>
>>[!done] Complessivamente:
>>$$S[i]=max\{ A[i],S[i-1]+A[i] \}$$

```pseudo
	\begin{algorithm}
	\caption{Max Subarray}
	\begin{algorithmic}
\Procedure{MaxSum}{$ A[1,\dots, n] $}
\State $ \text{new array} S $
\State $ S[1]=A[1] $
\State $ m=S[1] $
\For{$ i=2 \to n $}
  \State $ S[i]=max\{ A[i],S[i-1]+A[i] \} $
\State $ m=max\{m,S[i]\} $
 \EndFor
 \Return $ m $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

>[!caution] Complessità

$$
\Theta(n)
$$
#### Ricerca del Sottovettore
>*Siamo in grado di calcolare il valore della massima somma tra tutti i sottovettori di $A[1,\dots,n]$*

>[!question] Come determiniamo quale sottovettore produce tale somma?

- Abbiamo l'indice dell'***elemento finale del sottovettore***
- Possiamo ricavare l'indice iniziale ***procedendo a ritroso***

```pseudo
	\begin{algorithm}
	\caption{Find Max Subvector}
	\begin{algorithmic}
\Procedure{SearchStartIndex}{$ A[1,\dots,n],S[1,\dots,n], imax $}
\State $ i=imax $
\While{$S[i] \neq A[i]  $}
\State $ i=i-1 $
\EndWhile
\Return $ i $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```