## Pseudo Codice
---
```pseudo
	\begin{algorithm}
	\caption{Insertion Sort}
	\begin{algorithmic}
	\Procedure{InsetionSort}{$A[]$}
	\For{$ j=2 \to size(A)$}
  \State $ key=A[j] $
  \State $ i=j-1 $
  \While{$i>0 \text{ and } A[i]>key$}
  \State $ A[i+1]=a[i] $
  \State $ i=i-1 $
  \EndWhile
  \State $ A[i+1]=key $
 \EndFor
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

## Concetto
---
>Ad ogni passo ho una sottosequenza ordinata in cui inserisco un nuovo elemento dell'input

![[Pasted image 20240306181155.png]]