---
## Avvio del sistema operativo
---
### Round Robin
Basato sul concetto di quanto di tempo o time slice
- Si divide l'esecuzione del programma in diversi periodi di tempi di lunghezza uguale
	- Il processo rimane in esecuzione finché si ferma da solo o termina il suo quanto di tempo

L'insieme dei processi in stato di ready è organizzato come una coda
> due casi

1. Il processo lascia il processore volontariamente
2. Il processo esaurisce il suo time slice
	1. Viene reinserito in fondo alla coda dei processi ready

La durata del quanto di tempo è un parametro critico
- Se è breve, il sistema è poco efficiente
	- Deve cambiare processo attivo molto spesso
- Se è lungo, in presenza di numerosi processi pronti ci sono lunghi periodi di inattività per ciascun processo

È necessario che l'hardware fornisca un timer (interval timer) che agisce sull'interruzione della cpu

### Scheduling a priorità
Non tutti i processi sono tutti uguali

Soluzione:
- Si definisce ad ogni processo una specifica priorità
- Lo scheduler sceglie più spesso il processo pronto con priorità più alta

Priorità
- Definite dal sistema operativo
	- Utilizzate una o più quantità misurabili per calcolare la priorità di un processo
		- SJF è un sistema basato su priorità
- Definite esternamente
	- Non definite dal so, imposte dal livello utente

![[Pasted image 20241018113704.png]]
> divisione dei processi con diversa priorità in diverse code dei processi

Priorità statica
- La priorità non cambia ma i durante la vita di un processo
- problema: starvation

Priorità dinamica
- La priorità varia durante la vita del processo

Aging, tecnica ch econsiste nell'incrementare gradualmente la priorità dei processi in tattesa
- Nessun processo rimarrà in attesa per un tempo indefinito perché prima o poi raggiungerà la priorità massima

Scheduling multilivello
All'interno di ogni classe di processi è possibile usare una politica specifica adatta alla caratteristica della classe

- Processi server -> Priorità statica
- Processi utenti interattivi -> round robin
- Altri processi utente -> FIFO

## Scheduling Real time
In un sistema real time la correttezza dell'esecuzione non dipende solamnete dal valore del risultato del risultato ma anche dall'istante temporale nel quale il risultato viene emesso

Hard real time
- La deadline di esecuzione dei programmi non devono essere superate in nessun caso
	- Potrebbe causare effetti catastrofici il contrario
	- Centrali nucleari, sistemi di controllo nei veivolo

Soft realtime
- Errori occasionali sono tollerabili

Scheduler real time
- Earliest deadline first

Politica di scheduing per processi periodici real-time
Viene scelo di volta in volta il processo che ha la deadline più prossima
- VIene detto priorità dinamica perché la priorità relativa di due processi varia in momenti diversi

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

 