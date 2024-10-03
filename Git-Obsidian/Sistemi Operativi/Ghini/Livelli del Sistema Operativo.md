## Introduzione
---
>[!definizione] Sistema Operativo
>Il sistema operativo è un ***insieme di programmi*** che ***controllano*** l'esecuzione dei programmi applicativi e agisce come ***interfaccia*** tra le applicazioni e l'hardware del calcolatore

>[!caution] Scopo

> Lo scopo del sistema operativo è quello di consentire agli utenti e ai programmi di ***utilizzare le funzionalità dell'hardware***, assicurando tutte le necessarie ***garanzie di sicurezza***

#### Esempio di Programma in Esecuzione
>Quando un applicativo ha bisogno di ***leggere o scrivere*** in un file all'interno della macchina:

- Il programma fa una ***richiesta*** al *sistema operativo* di accedere ad un determinato file
- Il *sistema operativo* traduce la richiesta di lettura e scrittura in una ***serie di istruzioni macchina***
	- Queste istruzioni verificano ***dove si trova il dato*** e controlla se l'utente che utilizza il processo ha il ***diritto*** di andare a ***vedere*** il contenuto del file
- Infine il *sistema operativo* ***legge*** per conto del processo il contenuto, lo inserisce in un ***buffer*** nella `RAM`, per avere un accesso più veloce

## Sistema a Livelli
---
>[!info] Struttura a livelli
>Il *sistema operativo* è strutturato con 3 porzioni, divise come l'immagine che segue

![[OS-Levels.png]]

>Ogni livello mette a disposizione un ***livello di astrazione*** di servizio che può essere utilizzata dagli altri livelli
### Kernel
>[!info] Funzionalità
>Il ***kernel*** ha la *responsabilità* di interagire con l'hardware, è la porzione di *sistema operativo* che *interagisce* ***direttamente con l'hardware***
>>[!tip] Funzioni
>>Il ***kernel*** è utilizzato per la gestione: dei ***processi***, della memoria `RAM` e di *massa*, del ***file system*** e dell' input/output, sia fisico che via rete
>>- Per fare ciò il ***kernel*** utilizza delle *risorse* come *istruzioni macchina* riservate e ***strutture dati*** in memoria `RAM`

Il ***kernel*** svolge una operazione molto complessa e per ciò ha ***diritti maggiori*** di accesso all'*hardware*
- Per poter sfruttare *quasi* tutte le istruzioni macchina

>[!caution] "Modo Kernel"
>Quando il ***kernel*** è in esecuzione, la `CPU` è configurata per sfruttare quasi tutte le istruzioni disponibili

### Modo User
>[!Info]
>Nel "***modo user***" fanno parte due sezioni:
>- *Utilità di sistema*
>- *Librerie standard di sistema*

Entrambe queste due sezioni hanno ***accesso ad un insieme sempre più piccolo*** di istruzioni hardware
- Non hanno accesso a istruzioni ***con accesso pericoloso*** all'hardware

>[!question] Come fanno i programmi ad accedere alle funzioni hardware, se non hanno accesso diretto a tutte l istruzioni?

Il ***kernel*** mette a disposizione delle *funzionalità* che possono essere usate dai programmi degli utenti: le ***system call***

Quando un processo cerca di ***danneggiare*** altri processi o anche il *sistema operativo*, anche se per sbaglio:
>[!fail] il sistema operativo *termina istantaneamente il processo*
>Prevenendo l'esecuzione di operazione potenzialmente pericolosa

#### System Call

>[!Definizione]
>Le ***system call*** sono delle sequenze di istruzioni macchina eseguite dal *kernel*
>>[!summary] Quando un programma chiama una *system call*:
>>Il programma chiede di eseguire una "*funzione*" potenzialmente pericolosa
>>- Il ***controllo*** dell'esecuzione passa al *kernel*
>>	- cambia il modo di esecuzione della `CPU` da "*Modo User*" a "*Modo kernel*"

Si possono vedere come una "***interfaccia del kernel***"
- Il sistema operativo mette a disposizione le funzionalità che possono essere invocate di "***livelli superiori***"

Dipendono dal tipo di sistema operativo in esecuzione e dall'hardware della macchina
- Sono le ***librerie standard di sistema*** che "*traducono*" le operazioni generali e le mette in istruzioni ***specifiche per l'hardware***

## Distinzione tra Modo kernel e Modo Utente
---

>[!info] Stato di esecuzione
>La `CPU` è fatta per lavorare con uno stato di esecuzione:
>Quando la `CPU` è nello stato di livello di privilegio $0$, consente l'esecuzione di quasi tutte le operazioni
>>[!abstract] Differenza di privilegi
>>Più il livello di privilegio ***aumenta***, il *set di istruzioni* viene ***ristretto*** sempre di più
>>- Diminuisce man mano quello che la `CPU` è in grado di fare

![[Protection-Levels.png|400]]
> *Livello di privilegio / protezione*

Il livello $3$ è il livello di privilegio utilizzato quando viene usata una ***applicazione utente***

### Cambio di Livello di privilegio
> Nel momento in cui l'applicazione chiama una system call
 
Il meccanismo con cui la ***system call*** viene chiamata, cambia lo ***stato di esecuzione*** e il ***livello di privilegio*** della `CPU` per poter eseguire quella istruzione
- Quando la *system call* finisce, si esegue l'***operazione opposta***, torna al livello di protezione precedente

>[!info] Cambi Continui
>La `CPU` cambia continuamente il suo ***modo di protezione***
>- Il cambiamento viene fatto solo tramite ***chiamata o terminazione*** della *system call*
>>[!caution] Strumento di Cambiamento
>>Il cambiamento è fatto tramite "`interrupt`"

