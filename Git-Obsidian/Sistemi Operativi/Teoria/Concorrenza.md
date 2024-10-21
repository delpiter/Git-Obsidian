## Introduzione
---
> In un sistema operativo sono presenti un gran numero di attività che vengono eseguite più o meno ***contemporaneamente*** dal processore

>[!warning] Senza delle regole, la consistenza delle attività sarebbe ***difficile*** da descrivere e realizzare

>[!todo] Assioma di *Finite Progress*
>Ogni [[Processi, Schedule e Thread#Processi|processo]] viene eseguito ad una velocità ***finita***, ma ***sconosciuta***


>[!question] Che cos'è la ***concorrenza***?

>La concorrenza riguarda la gestione di *processi multipli*

Esistono 3 modalità di gestione di processi multipli
### Multiprogramming
>[!info] Definizione
>Nel ***Multiprogramming*** è presente un solo processore ma più processi
>- I processi multipli sono *alternati nel tempo*, ad ogni istante al massimo un processo è in esecuzione
>
>>[!note] Il *parallelismo* è apparente

>[!abstract] Concetto: ***Interleaving***
>I processi sono alternati con una velocità tale da dare l'impressione di avere un multiprocessore

![[Interleaving.png]]


![[Overlapping.png]]
