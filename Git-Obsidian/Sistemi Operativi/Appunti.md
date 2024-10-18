---
## Avvio del sistema operativo
---
## Concorrenza
Introduzione
In un sistema operativo sono presenti un gran numero di attività che vengono eseguiti più o meno contemporaneamente dal processore e dai dispositivi presenti in un elaboratore

Senza delle regole, la consistenza delle attività sarebbe difficile da descrivere e realizzare

Processo
- Una attività controllata da un programma che si svolge su un processore
	- Programma entità statica
		- Insieme di istruzioni
	- Processo entità dinamica
		- Rappresenta Il modo in cui il programma viene eseguito nel tempo

Assioma di finite progress
- Ogni processo viene eseguito ad una velocità finita ma sconosciuta


Ad ogni istante un processo può essere interamente descritto dalle seguenti componenti
- La sua immagine di memoria
- La sua immagine nel processore
- Lo stato di avanzamento

cos'è la concorrenza

Riguarda la gestione di processi multipli
- Multiprogramming
	- Un processore, più processi
		- I processi multipli sono "alternati nel tempo", ad ogni istante al massimo un processo è in esecuzione
		- Interleaving
	- Parrallelismo apparente
- Multiprocessing
	- Più processi su una macchina con processori multipli
	- Più processi vengono eseguiti simultaneamente su processori diversi
		- I processi sono alternati nello spazio
		- Overlapping
	- parallelismo reale
- Distributed processing
	- Più processi su un insieme di computer distribuiti e indipendenti
	- Parallelismo reale

Esecuzione concorrente
- Due programmi si dicono in esecuzione concorrente se vengono eseguiti in parallelo (con parallelismo reale o apparente)

Concorrenza
- È l'insieme di notazioni per descrivere l'esecuzione concorrente di due o più programmi
- È l'insieme di tecniche per risolvere i problemi associati all'esecuzione concorrente, quali comunicazione e sincronizzazione

Dove si può trovare la concorrenza
- Applicazioni multiple
- Applicazioni strutturate su processi
	- Alcune applicazioni possono essere progettate come un insieme di processi o thread concorrenti
- Struttura del sistema operativo
	- Funzioni del sistema operativo implementate come un insieme di processi o thread

Parallelizzazione reale e apparenti sono differenti??
- Per come è fatta la gestione dei dati e il sistema operativo le differenze non ci sono

Non c'è differenza sostanziale fra i problemi relativi a multiprogramming e multiprocessing

 I problemi derivano dal fatto che non è possibile predire gli istanti temporali in cui vengono eseguite le istruzioni
- I due processi accedono ad una o più risorse condivise

Race condition
Definizione
- Si dice che un sistema di processi multipli presenta una race condition qualora il risultato finale dell'esecuzione dipenda dalla temporizzazione con cui vengono eseguiti i processi
	- per scirvere un programma concorrente, si deve eliminare la race condition