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
