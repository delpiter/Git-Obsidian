## Alberi di Copertura Minima
---
>[!info] *MST*
>Problema: 
>Dato un grafo $G$ trovare un albero $T$ tale che la somma dei pesi associati agli archi di $T$ sia minima
>>[!tldr] Input
>>Un [[I Grafi#Grafo Pesato|Grafo Pesato]] $G=(V,E,W)$
>
>>[!caution] Output
>>Un ***albero di copertura minimo*** $T$
>>- $T=(V,E',W')$ tale che $\displaystyle\sum_{w\in W'}w$ è minima

Ci sono 2 algoritmi [[Gli Algoritmi Greedy|greedy]] per calcolare un `MST`
- Entrambi basati su uno ***stesso algoritmo generale***

L'*algoritmo* costruisce l'insieme $A$ degli archi dell'`MST` partendo dall'***insieme vuoto*** e aggiungendo di volta in volta un arco $a$ tale che $A\cup a$ sia sottoinsieme degli archi di un `MST`

Gli algoritmi differiscono per il modo in cui viene ***cercato l'arco da aggiungere***

### Algoritmo di Kruskal
#### Kruskal: Pseudocodice
```pseudo
	\begin{algorithm}
	\caption{Kruskal's Algorithm}
	\begin{algorithmic}
	\Procedure{MST-Kruskal}{$ G,w $}
\State $ A=\varnothing $
\ForAll{$\text{vertex }v\in V[G]$}
\State \Call{ Make-Set }{$ v $}
\EndFor
\State $\text{sort the list of edges into monotonically increasing order by weight }w$
\ForAll{$\text{edge }(u,v)\text{ taken from the sorted list in order}$}
\If{\Call{ Find-Set }{$ u $}$\neq$ \Call{ Find-Set }{$ v $}}
  \State $ A = A \cup \{(v,u)\}$
 \Call{ Union }{$ u,v $}
 \EndIf
\EndFor
\Return $ A $
 \EndProcedure
	\end{algorithmic}
	\end{algorithm}
```
##### Esempio
![[Kruskal-1.png]]
![[Kruskal-2.png]]
![[Kruskal-3.png]]
![[Kruskal-4.png]]

#### Kruskal Correttezza
>[!Teorema]
>Sia $G(V,E,W)$ il grafo dato in *input*
>Sia $G'(V,E',W')$ il sottografo di qualche `MST` di $G$, contenente tutti i vertici e alcuni archi di $G$ (***non*** è un *albero di copertura*, rimangono ***vertici isolati***)
>Sia $G_{1}(V_{1},E_{1},W_{1})\cup G_{2}(V_{2},E_{2},W_{2})$ una partizione di $G'$ in due componenti non connesse (***taglio*** di $G$)
>Sia $e\in E$ un arco di peso minimo che connette $G_{1}$ e $G_{2}$
><u>Allora</u>
>Anche $G'(V,E'\cup \{ e \},W'\cup\{ w_{e} \})$ è un sottografo di qualche `MST`

>[!abstract] Sia $T'$ un `MST` contenente $e'$

Se $W(e')\geq W(e)$, e si sostituisce $e'$ con $e$ si ottiene un altro albero di copertura $T$ con $W(T')\geq W(T)$

Quindi $T$ sarebbe un albero di copertura di costo inferiore a $T'$:
- O $W(e')=W(e)$
- Oppure $T'$ non era un `MST`

#### Completezza
>*L'algoritmo si divide in diverse parti*

>[!abstract] Inizializzazione

$$
O(V)
$$
>[!caution] Ordinamento Archi

$$
O(E\cdot lg(E))
$$
>[!todo] Operazioni nella Foresta di [[Insiemi Disgiunti]]

$$
O(E)
$$

>[!done] Tempo Complessivamente richiesto per la costruzione

$$
O(E\alpha(E,V))
$$
O anche:
$$
O(E\cdot lg^*(V))
$$
- Operazioni su [[Insiemi Disgiunti#Strutture Dati per Insiemi Disgiunti|Up Tree]]


>[!info] Complessità Finale

$$
T(V,E)=O(V)+O(E\cdot log(E))+O(E\cdot log^*(V))=O(E\cdot log(E))
$$