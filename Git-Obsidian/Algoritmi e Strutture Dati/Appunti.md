# `26/02/2024

## Argomenti da Finire
- Analisi asintotica
- Algoritmi ricorsivi
- Linear Select
- Dimostrazioni di Algoritmi di Sort

## Analisi asintotica
Obbiettivo
- Semplificare l'analisi del consumo di risorse di un algoritmo prescindendo dai dettagli implementativi o di altro genere
- Classificare gli algoritmi in base al loro comportamento asintotico

## Algoritmi Ricorsivi
```pseudo
	\begin{algorithm}
	\caption{Binary Search}
	\begin{algorithmic}
	\Procedure{BinarySearch}{$val,v[],i,j  $}
\If{$ i>j  $}
  \Return $ -1 $
  \Else 
 \State $ m=(i+j)/2 $
 \If{$ v[m]==val  $}
 \Return $ m $
 \Else 
 \If{$ v[m]>val  $}
  \Return \Call{BinarySearch}{$val,v,i,m-1$}
  \Else 
 \Return \Call{BinarySearch}{$val,v,m+1,j$}
 \EndIf  
 \EndIf
 \EndIf
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

```pseudo
	\begin{algorithm}
	\caption{Find Max}
	\begin{algorithmic}
	\Procedure{FindMax}{$v[],Max,i$}
	\If{$i == v.count$}
	  \Return $ Max $
	  \Else 
	 \If{$ v[i+1] > Max  $}
	  \Return \Call{FindMax}{v,v[i+1],i+1}
	  \Else 
		\Return \Call{FindMax}{v,Max, i+1}
 \EndIf
 \EndIf

 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

[Graph Editor (csacademy.com)](https://csacademy.com/app/graph_editor)



