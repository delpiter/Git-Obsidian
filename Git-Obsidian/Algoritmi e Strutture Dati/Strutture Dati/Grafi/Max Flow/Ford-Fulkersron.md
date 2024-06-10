## Algoritmo di Ford-Fulkerson
---
>[!info] Algoritmo
>L'algoritmo di ***Ford-Fulkerson*** è un [[Gli Algoritmi Greedy|algoritmo greedy]] che risolve il problema dei [[Problema|flussi massimi]]
>>[!example] Funzionamento
>>1. *Set* $f(u,v)=0\qquad \forall (u,v)\in A$
>>2. Trova un ***cammino aumentante*** $P$ nel grafo residuo $G_{f}$
>>3. Aumenta il flusso su $P$ e aggiorna $G_{f}$
>>4. Ripeti 2-4 finchè possibile

>[!warning] Problema

È possibile, usando questo algoritmo, che ad un qualsiasi step venga scelto un cammino "*sbagliato*", da cui da quel punto in poi non è più possibile trovare la soluzione migliore
- Per risolvere questo problema è necessario ampliare la definizione di [[Problema#Grafo Residuo|capacità residua]]

>[!abstract] Capacità Residua, Ampliamento
>Ridefiniamo la ***Capacità Residua***:
>La capacità residua è definita sia ***riducendo la capacità del flusso***, sia ***aumentando la capacità del flusso nell'arco opposto***
>$$c_{f}(u,v)=\begin{cases}c(u,v)-f(u,v)\quad \text{ direzione }u\to v \\c(u,v)+f(u,v)\quad \text{ direzione }v\to u\end{cases}$$

![[Revisited.png]]
