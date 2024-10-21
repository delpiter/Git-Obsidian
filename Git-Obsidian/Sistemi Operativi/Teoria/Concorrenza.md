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

### Multiprocessing
>[!info] Definizione
>Nel ***Multiprocessing*** sono presenti un più processori
>- I processi vengono eseguiti simultaneamente
>
>>[!note] Il *parallelismo* è reale

>[!abstract] Concetto: ***Overlapping***
>I processi sono "sovrapposti" nel tempo, si definisce "*overlapping*" la sovrapposizione temporale dei processi

![[Overlapping.png]]

### Distributed Processing
>[!info] Definizione
>Nel ***Distributed Processing*** più processi vengono eseguiti su un insieme di computer distribuiti e indipendenti
>
>>[!note] Il *parallelismo* è reale

## Esecuzione Concorrente
>[!example] Definizione
>Due programmi si dicono in ***esecuzione concorrente*** se vengono eseguiti in parallelo, con parallelismo **reale** o **apparente**
>>[!abstract] Concorrenza
>>La concorrenza è l'insieme di tecniche per risolvere i problemi associati all'esecuzione concorrente, come la *comunicazione* e la *sincronizzazione*

>[!question] Dove si può trovare la concorrenza?

1. Nelle applicazioni multiple
2. Nelle applicazioni strutturate su processi
3. Nella struttura del sistema operativo

>[!caution] Ci sono differenze tra parallelismo reale e apparente?

>Per come è fatta la gestione dei dati e il sistema operativo, non c'è alcuna differenza

I problemi derivano dal fatto che ***non*** è possibile *predire* gli istanti temporali in cui vengono eseguite le istruzioni
- Due processi potrebbero accedere ad una o più risorse condivise *contemporaneamente*

#### Race Condition
>[!info] Definizione
>Si dice che un sistema di processi multipli presenta una ***race condition*** qualora il risultato finale dell'esecuzione *dipenda* dalla temporizzazione con cui vengono eseguiti i processi
>- Per scrivere un programma concorrente si deve **eliminare** la *race condition*

