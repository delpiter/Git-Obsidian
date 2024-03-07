## Pseudocodice
---
```pseudo
	\begin{algorithm}
	\caption{Quick Sort}
	\begin{algorithmic}
	\Procedure{QuickSort}{$ A[],p,r $}
	\If{$ p<r  $}
	  \State $q=$\Call{Pivot}{$A,p,r$}
	  \State $j=$\Call{Partition}{$A[],p,q,r$}
	  \State \Call{QuickSort}{$A[],p,j$}
	  \State \Call{QuickSort}{$A[],j+1,r$}
 \EndIf

 \EndProcedure
 \Procedure{Swap}{$A[],i,j  $}
\State $ tmp =A[i] $
\State $ A[i]=A[j] $
\State $ A[j]=tmp $
 \EndProcedure
 \Procedure{Partition}{$ A[],p,q,r $}
 \State $ i=p $
 \State $ j=r $
 \State $ pivot=A[q] $
 \State \Call{Swap}{$A[],p,q$}
 \While{$i<j$}
 \While{$j>p\text{ and }pivot \leq A[j] $}
 \State $ j=j-1 $
 \EndWhile
  \While{$i>r\text{ and }pivot > A[i] $}
 \State $ i=i+1 $
 \EndWhile
 \If{$ i<j  $}
 \State \Call{Swap}{$A[],i,j$}
 \EndIf
 \EndWhile
 \State \Call{Swap}{$A[],p,j$}
 \State \Return $ j $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```
![Quick Sort (LR pointers) (youtube.com)](https://www.youtube.com/watch?v=8hEyhs3OV1w)

## Concetto
---
>Algoritmo di ordinamento basato sulla tecnica [[Divide et Impera]]

Ideato da *Tony Hoare* nel 1960, come studente presso la *Moscow State University*
- Implementato come *algoritmo di ordinamento standard* nella libreria `C` di Unix (**`qsort()`**)
A differenza del [[Merge Sort]] il *quick sort* esegue comparazioni prima della ricorsione.

### Partition
La funzione di *partition* è la parte cruciale dell'algoritmo
Per trovare le partizioni:
- Imposto $i$ come indice del primo elemento
- Imposto $j$ come indice dell'ultimo elemento

1. Sposto $i$ a destra (`i++`) finché non trovo un elemento che è $\geq$ del *pivot*
2. Sposto $j$ a sinistra (`j--`) finché non trovo un elemento che è $<$ del *pivot*
3. Inverto gli elementi in posizione $i$ e $j$
4. Ripeto il processo fino a quando `j<i`

Quando noto che `j<i` ho separato con successo il vettore in due sottovettori 
- Il sottovettore di sinistra contenente solo valori $\leq$ *pivot*
- Il sottovettore di destra contenente solo valori $>$ *pivot*

![[Pasted image 20240307131522.png]]

## Costo Computazionale
---
### Caso Ottimo
>[!done] Partizioni Bilanciate

Come *pivot* viene scelto sempre l'elemento mediano
- Di conseguenza la complessità computazionale sarà uguale a quella del [[Merge Sort]]
$$
T(n)=2T(n/2) +\Theta(n)
$$
- Quindi $T(n)=\Theta(nlog(n))$

### Caso Pessimo
>[!danger] Partizioni Sbilanciate

Come *pivot* viene scelto sempre il valore *min/max* del vettore
- Ogni divisione rimuove solamente un elemento

$$
T(n)=T(n-1)+\Theta(n)
$$
- Quindi $T(n) =\Theta(n^2)$

### Caso Medio
>[!question] Partizioni Sproporzionate

Analizzando, noteremo che il caso medio dell'algoritmo *quick sort* è molto più vicino al caso ottimo rispetto al caso pessimo.

>Supponiamo che ogni partizione produce una separazione proporzionale $9-to-1$
>Ad una prima occhiata sembra abbastanza sbilanciato

Otteniamo la seguente equazione ricorsiva
$$
T(n) = T(n/10)+T(9n/10)+\Theta(n)
$$
![[Pasted image 20240307142205.png]]
*Albero della ricorsione del quick sort*

Possiamo notare come la parte sinistra dell'albero si concluda con una altezza di solo:
- $log_{10}n$
La ricorsione, però si conclude solo quando il lato destro dell'albero ha raggiunto la fine
$$
\begin{array}
\ \frac{n}{\left( \frac{10}{9} \right)^k}=1 \implies n=\left( \frac{10}{9} \right)^k \\
log_{\frac{10}{9}}n=k
\end{array}
$$
- La ricorsione quindi si conclude al livello $log_{\frac{10}{9}}n$ che in termini di costo computazionale è $\Theta(log(n))$

 Di conseguenza, nel caso medio, il *quick sort* ha un costo computazionale di $\Theta(n log(n))$

## Distribuzione dell'input
---
Abbiamo assunto implicitamente che tutte le sequenze di numeri da ordinare fossero equiparabili. 
- Se ciò non fosse vero potremmo avere dei costi computazionali diversi per input diversi

>[!done] Soluzione

### RQS
> Il *randomized quick sort* usa una versione randomizzata della procedura ***partition***

Ad ogni chiamata il *pivot* viene scelto in maniera casuale
- Un algoritmo randomizzato non ha un input pessimo, ma ha una sequenza di scelte pessime di *pivot*

### Conclusione
La probabilità del caso pessimo del *quick sort* è incredibilmente ridicola
- Possiamo dire quindi che l'efficienza del *quick sort* è simile a quella del [[Merge Sort]]
