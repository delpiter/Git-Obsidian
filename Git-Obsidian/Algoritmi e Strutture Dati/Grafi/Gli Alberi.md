## Alberi: Definizione
---
>[!info] Alberi
>Un *albero* è un [[I Grafi#Grafo Definizione|grafo]] aciclico, con un numero di nodi uguale al numero di archi più uno.
>$$\left| E \right| = \left| V \right|-1  $$
>>[!done] Alternativa Equivalente
>
>Un albero è un grafo aciclico totalmente connesso
>Può esistere un nodo particolare chiamato *radice*
>- La radice **induce implicitamente** un *ordinamento parziale* fra i nodi

## Definizioni sugli Alberi
---
> Se c'è un nodo radice viene implicitamente definita una relazione di *ordinamento* fra nodi basata sulla *distanza dalla radice*.

### Elenco proprietà Alberi
- Ogni nodo non radice ha un unico ***predecessore/padre***
	- Unico arco *entrante*, che proviene dalla radice
- Un nodo può avere più ***successori/discendenti/figli***
- Un nodo senza successori è detto *foglia*
- La *profondità di un nodo* è la lunghezza del cammino dalla radice al nodo
- L'*altezza di un nodo* è la massima lunghezza del cammino dal nodo a una foglia discendente del nodo
- L'*altezza di un albero* è l'altezza della nodo radice
- Un *livello/strato* di un albero consiste nell'insieme di tutti i nodi con la stessa *profondità*
- Il *numero di livelli* di un albero è pari alla sua *altezza* +1

>[!info] Arborescenza
>Una *arborescenza* è un albero in un grafo orientato
>L'orientamento deve essere sempre diretta verso i nodi foglia

### Albero Binario
>[!info] Definizione
>In un *albero binario* ogni nodo ha **zero**, **uno** o due **successori** ordinati
>
>>[!tip] Albero Binario **Completo**
>>Tutte le foglie hanno la stessa profondità e tutte le profondità sono completamente piene
>
>>[!tip] Albero Binario ***Quasi*** **Completo**
>>Albero Binario completo tranne che per il livello inferiore che è pieno da sinistra verso destra solo parzialmente

#### Alberi Binari Quasi Completi
> Si consideri un albero binario quasi completo di altezza $h$

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
	- Quindi per ottenere il vero livello dell'albero si dovrà arrotondare il numero per eccesso

