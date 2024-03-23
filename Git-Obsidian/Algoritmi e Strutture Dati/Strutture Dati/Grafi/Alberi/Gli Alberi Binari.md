## Albero Binario
---
>[!info] Definizione
>In un *albero binario* ogni nodo ha **zero**, **uno** o due **successori** ordinati
>
>>[!tip] Albero Binario **Completo**
>>Tutte le foglie hanno la stessa profondità e tutte le profondità sono completamente piene
>
>>[!tip] Albero Binario ***Quasi*** **Completo**
>>Albero Binario completo tranne che per il livello inferiore che è pieno da sinistra verso destra solo parzialmente

### Alberi Binari Quasi Completi
> *Si consideri un albero binario quasi completo di altezza* $h$

>[!example] Se il livello inferiore contiene **1 elemento**

Il numero di elementi $n$:
$$
n=(1+2+4+\dots+2^{h-1})+1 = \displaystyle{\frac{2^{h+1}-1}{2-1}}+1= (2^h-1)+1 = 2^h
$$
>[!example] Se il livello inferiore è pieno

Il numero di elementi $n$:
$$
n=1+2+4+\dots+2^h = \displaystyle{\frac{2^{h+1}-1}{2-1}} = 2^{h+1}-1
$$

>[!done] Range del numero di Elementi

In ogni caso il numero di elementi sarà:
$$
2^h\leq n<2^{h+1}-1
$$
Di conseguenza:
$$
\begin{array}
\ h\leq log(n)< h+1 \\
log(n)-1 < h \leq log(n) \\
h = \lceil log(n) \rceil 
\end{array}
$$
>[!question] Perchè $\lceil log(n) \rceil$?

Prendiamo $n$ come numero di nodi $+1$ di un albero binario
- $log(n)=$ altezza dell'albero completo
- L'altezza di un albero *quasi completo* è la stessa
	- Di conseguenza $log(n)$ di un albero *quasi completo* si otterrebbe un numero decimale, inferiore a quello del vero valore del livello
	- Quindi per ottenere il vero livello dell'albero si dovrà ***arrotondare il numero*** per *eccesso*

## Alberi Binari di Ricerca
---
>[!info] Definizione
>Un ***binary search tree*** (**BST**) è una *struttura dati* ad *albero binario* con delle particolari proprietà
>Le chiavi in un *binary search tree* sono sempre salvate in modo da soddisfare queste proprietà
>>[!abstract] Proprietà
>>Sia $x$ un nodo in un *binary search tree*
>>Se $y$ è un nodo del ***sotto albero di sinistra***
>><u>Allora</u>
>>Deve valere la relazione:
>>$$x.key\geq y.key$$
>>Sia $x$ un nodo in un *binary search tree*
>>Se $y$ è un nodo del ***sotto albero di destra***
>><u>Allora</u>
>>Deve valere la relazione:
>>$$x.key\leq y.key$$
 
>[!question] Quanti *binary search tree* esistono con $n$ nodi?

Il numero di *binary search tree* possibili con $n$ nodi è rappresentato con la seguente funzione dei ***Numeri di Catalan***
- [[Definizioni_Analisi#Coefficiente Binomiale|Coefficiente binomiale]]
$$
C_{n}=\displaystyle{\frac{1}{n+1}}\binom{2n}{n}
$$

### Operazioni
>[!example] Operazioni in un **BST**
>Un *binary search tree* ha a disposizione un set di operazioni:
>1. Search
>2. Minimum
>3. Maximum
>4. Predecessor
>5. Successor
>6. Insert
>7. Delete

>[!warning] Nota Bene

Un albero di ricerca binaria non è sempre ***ben bilanciato***:
![[Pasted image 20240323114207.png]]
- Potrebbe accadere che i nodi siano *prevalentemente* da un *lato dell'albero*
![[Pasted image 20240323114233.png]]
- In questo caso il [[Complessità di Algoritmi#Analisi di Complessità|costo computazionale]] delle *operazioni è più alto*


### Rappresentazione con Array
>[!info] Convenzione
>Anche gli alberi binari come lo [[Heap]] possono essere rappresentati con un vettore.
>Con la convenzione sugli **indici dei figli**.
>I *binary search tree* non sono alberi binari *quasi* completi
>- Ciò porta ad avere delle ***celle vuote*** all'interno dell'*array*

### Ordinamento
#### Inorder Tree Walk
```pseudo
	\begin{algorithm}
	\caption{Inorder Tree Walk}
	\begin{algorithmic}
\Procedure{Inorder-Tree-Walk}{$ x $}
\If{$ x\neq \text{ NULL }  $}
  \State \Call{Inorder-TreeWalk}{$left[x]$}
  \State \Print key[x]
  \State \Call{Inorder-TreeWalk}{$right[x]$}
 \EndIf
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

#### Preorder Tree Walk
```pseudo
	\begin{algorithm}
	\caption{Preorder Tree Walk}
	\begin{algorithmic}
\Procedure{Preorder-Tree-Walk}{$ x $}
\If{$ x\neq \text{ NULL }  $}
\State \Print key[x]
  \State \Call{Preorder-TreeWalk}{$left[x]$}
  
  \State \Call{Preorder-TreeWalk}{$right[x]$}
 \EndIf
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

#### Postorder Tree Walk
```pseudo
	\begin{algorithm}
	\caption{Postorder Tree Walk}
	\begin{algorithmic}
\Procedure{Postorder-Tree-Walk}{$ x $}
\If{$ x\neq \text{ NULL }  $}
  \State \Call{Postorder-TreeWalk}{$left[x]$}
  \State \Call{Postorder-TreeWalk}{$right[x]$}
  \State \Print key[x]
 \EndIf
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```

