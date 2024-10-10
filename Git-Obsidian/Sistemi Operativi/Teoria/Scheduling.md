## Scheduler, Processi e Thread
---
### Processi
>[!question] Qual è la manifestazione fisica di un processo?

- Il segmento di ***codice*** da eseguire
- I ***dati*** su cui operare
- Uno ***stack*** di lavoro per la gestione di chiamate di funzione, etc...
- Un ***insieme di attributi*** contente tutte le info necessarie per la gestione del processo stesso

>[!done] Questo insieme di attributi prende il nome di Process Control Block


![[ProcessInMemory.png|150]]
![[MemoryExample.png]]


- Ogni processo ha un ***descrittore associato***
- L'insieme dei descrittori è ***contenuto in una tabella***

>[!abstract] Divisione delle informazione nel descrittore
>1. Informazioni di ***identificazione di processo***
>2. Informazioni di ***stato del processo***
>3. Informazioni di ***controllo del processo***
#### Descrittori di processo
##### Informazione di identificazione di un processo
>[!info] Process ID
> Il ***process id*** è un identificatore di processo o `PID`

Può essere:

>[!abstract] Identificatore di processo
- Semplicemente un indice in una ***tabella di processi***
- Un ***numero progressivo***
- Molte tabelle usano il `PID` per ***identificare un elemento*** della tabella dei processi

>[!abstract] Identificatore di altri processi logicamente collegati al processo

- Identificatore del processo padre

>[!abstract] Identificatore dell'utente che ha richiesto l'esecuzione

##### Informazioni di stato del processo
> ***Registri generali*** del processore

> ***Registri speciali***, (program counter e registri di stato)

##### Informazioni di controllo del processo
>[!info] Informazioni di scheduling
>Indica lo stato del processo
>- ***In esecuzione - Pronto - In attesa***

***Gestione della memoria***
- Valori dei registri di base

***Informazioni di accounting***
- Tempo di esecuzione e trascorso dall'attivazione

***Informazioni relative alle risorse***

***Informazioni per interprocess communication***
- *Semafori*

### Scheduler
>[!abstract] Scheduler
>Lo ***scheduler*** è la componente più importante del [[Livelli del Sistema Operativo#Kernel|kernel]]
>*Gestisce* quale processo deve essere in ***esecuzione*** ad ogni istante
>Interviene quando viene richiesta o termina un'operazione di `I/O`

>[!done] Precisione delle parole

##### Schedule
>Lo ***schedule*** è la sequenza temporale di assegnazioni delle risorse da gestire ai richiedenti

##### Scheduling
>Lo ***scheduling*** è l'azione di calcolare uno *schedule*

##### Scheduler
>Lo ***scheduler*** è la componente software che calcola lo *schedule*

#### Mode Switching e Context Switching
>Ogni volta che avviene un ***interrupt*** il processore è soggetto ad un [[Livelli di Sicurezza#Cambio di Livello di privilegio|mode switching]]

Se lo *scheduler* decide di eseguire un altro processo il sistema è soggetto ad un ***context switching***
- Lo stato del ***processo attuale*** viene salvato nel `PCB` corrispondente
- Lo stato del ***processo selezionato*** per l'esecuzione viene caricato dal `PCB` nel processore

![[ContextSwitch.png]]

#### Stati dei Processi

>[!caution] Running
>Il Processo è in esecuzione

>[!abstract] Waiting
>Il processo è in ***attesa*** di qualche ***evento esterno***

>[!done] Ready
>Il processo può ***essere eseguito***, ma attualmente il processore è ***impegnato in altre attività***

![[ProcessStates.png]]
