## Catturone
---
Il kernel è la porzione di sistema operativo che si interfaccia con l'hardware

Il sistema operativo mette a disposizione le system call, specifiche per l'hardware
- Sono le librerie standard di sistema, che "traducono" le operazioni generali e le mette in istruzioni specifiche per l'hardware

Il kernel del sistema operativo mette a disposizione delle funzionalità che possono essere usate dai programmi degli utenti
- Vengono chiamate System Call

Sopra al livello del kernel
- C'è una "interfaccia di programmazione" (interfaccia delle system call) che mette a disposizione delle funzionalità che possono essere chiamate dai livelli superiori
L'hardware stesso mette a disposizione una interfaccia per interagire con l'interfaccia


Ciascuno dei livelli espone una interfaccia per i livelli superiori

58:00 1:28:00

Livello privilegio 0, la CPU consente l'esecuzione di tutte le istruzioni macchina messe a disposizione
- livello 1 vengono messe alcune restrizioni
- All'aumentare del livello di privilegio, diminuisce il numero di istruzioni macchina eseguibili
	- All'interno dell'esecuzione di una applicazione utente, il livello di privilegio cambia numerose volte e il controllo dell'esecuzione passa al livello inferiore
	- A fine esecuzione della istruzione "privilegiata" si avvia un meccanismo di ritorno al livello di privilegio precedente


## 23/09/2024
---
![[Pasted image 20241001094503.png]]
Lo scopo del sistema operativo è quello di consentire agli utenti e ai programmi di utilizzare le funzionalità l'hardware, assicurando tutte le necessarie garanzie di sicurezza
-

programma in esecuzione tipo:
Quando un applicativo ha bisogno di leggere o scrivere in un file all'interno della macchina:
- Il programma fa una richiesta al sistema operativo di accedere ad un determnato file
- Il so traduce la richiesta di lettura e scrittura in una serie di istruzioni macchina che verificano dove si trova il dato, controlla se l'utente che utilizza il processo ha il diritto di andare a vedere il contenuto di questo file
- Infine il so legge per conto del processo il contenuto, inserisce il contenuto in un buffer nella ram, per avere un accesso più veloce

Il so è strutturato con 3 porzioni
- kernel
	-  ha la responsabilità di interagire con l'hardware 
	- è la porzione di so che si interfaccia direttamente con l'hardware
	- per la gestione di processi, gestione di mem ram e di massa , gestisce il file system, input output fisico o via rete
		-  Per fare ciò il kernel utilizza delle risorse (istruzioni macchina e strutture dati in memoria ram)
	- Svolge una operazione molto complessa, ha diritti maggiori di accesso all'hardware, per sfruttare quasi tutte le istruzioni macchina
	- "Modo kernel": quando il kernel è in esecuzione la cpu è configurata per sfruttare quasi tutte le istruzioni disponibili
		- Esistono istruzioni macchina riservate anche al kernel
- "modo user"
	- Utilità di sistema
	- Librerie standard di sistema
		- Entrabe queste due sezioni hanno accesso ad un insieme sempre più piccolo di istruzioni hardware
		- Non hanno accesso a istruzioni con accesso pericoloso all'hardware

>[!question] Come fanno i programmi ad accedere alle funzioni hardware, se non hanno accesso diretto a tutte l istruzioni?

Il kernel mette a disposizione delle funzionalità "system call"
- Le system call sono delle sequenze di istruzioni macchina eseguite dal kernel
- Quando un programma chiama una system call, chiede di eseguire una "funzione"
- quando una programma chiama una system call (chiamate a funzioni potenzialmente pericolose) il controllo dell'esecuzione passa al kernel
	- Cambia il modo di esecuzione della cpu: da modo user a modo kernel
- Si possono vedere come una "interfaccia del kernel" con cui il sistema operativo mette a disposizione le funzionalià che possono essere invocate da chi "sta sopra"
Dipendono dal tipo di sistema operativo in esecuzione e dall'hardware della macchina

per poter consentire all'utente di scrivere un programma ad alto livello, il sistema operativo mette a disposizione delle librerie standard di sistema (libc)
- Librerie che implementano delle funzioni basiche che sono implementate in modo tale da chiamare le system call nel modo previsto dal kernel del so che stiamo operando


Ogni livello mette a disposizione un livello di astrazione di servizio che può essere utilizzata dagli altri livelli

## Distinzione tra modo kernel e modo utente
---
Livello di privilegio / protezione![[Pasted image 20241001101612.png]]

La cpu è fatta per lavorare con uno stato di esecuzione:
- Quando la cpu è nello stato di livello di privilegio 0
	-  Consente l'esecuzione di quasi tutte le operazioni
		- Sia semplici o complesse
- Più il livello di privilegio aumenta, il set di istruzioni viene ristretto man mano
	- Diminuisce man mano quello che la cpu può fare
- Livello 3 è il livello di privilegio utilizzato quando viene usata una applicazione utente
	- nel momento in cui l'applicazione chiama una system call, il meccanismo con cui la system call viene chiamata, cambia lo stato di esecuzione e il livello di privilegio della cpu per poter eseguire quella istruzione
	- Quando la sys call finisce, esegue l'operazione opposta, torna al livello di protezione precedente

La cpu cambia continuamente il suo modo di protezione
- Il cambiamento viene fatto solo tramite chiamata o terminazione di system call
- Il cambiamento è fatto tramite "`interrupt`"/ le system call, vengono chiamate per mezzo di `interrupt`

Quando un processo, cerca di danneggiare altri processi o anche il so, anche per sbaglio, il sistema operativo termina istantaneamente il processo, prevenendo l'esecuzione di operazione potenzialmente pericolosa

![[Pasted image 20241001103334.png]]L'hardware è "pilotato dal kernel"


Librerie e chiamate di sistema
- Le chiamate di sistema forniscono ai processi i servizi offerti dal so
	- Controllo dei processi, gestione dei file e dei premessi, gestioni dispositivi io
- Il modo in cui sono realizzate cambia al variare della cpu e del sistema operativo
- Il modo di utilizzo cambia al variare del so e della cpu
- Sono utilizzate direttamente utilizzando linguaggi di basso livello
- Possono essere chiamate indirettamente utilizzando linguaggi di alto livello
- L'insieme di tali funzioni di libreria rappresentano le API, l'interfaccia che il so offre ai programmi di alto livello
- Le librerie messe a disposizione dal so sono dette librerie di sistema
	- Cambiando sistema operativo o cambiando processore i nomi delle funzioni delle api rimangono gli stessi ma cambia il modo di invocare le system call

Alcune api modlto diffuse
- Win32 (windows), POSIX (unix), java API (JVM)
![[Pasted image 20241001104841.png]]

>[!question] Quali  system call utilizza un eseguibile?

Su linux esiste un comando che permette di vedere quali system call sono usate da un programma in esecuzione

```bash
strace command
```

esegue il comando specificato come argomento fino a che questo termina
- Intercetta e visualizza le system call che sono chiamate dal processo e i segnali che sono ricevuti dal processo

```bash
strace ifconfig 

execve("/sbin/ifconfig", ["ifconfig"], [/* 52 vars */]) = 0 brk(NULL) = 0x12f3000 
access("/etc/ld.so.nohwcap", F_OK) =-1 ENOENT(No such file or directory) 
mmap(NULL, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS,-1, 0) = 0x7f37cb8ee000 access("/etc/ld.so.preload", R_OK) =-1 ENOENT(No such file or directory) 
open("/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3 fstat(3, {st_mode=S_IFREG|0644, st_size=71665, ...}) = 0 
mmap(NULL, 71665, PROT_READ, MAP_PRIVATE, 3, 0) = 0x7f37cb8dc000 close(3
```

## Avvio del sistema operativo
---
Durante l'operazione di bootstrap, vengono eseguite delle istruzioni presenti nella rom che vanno a caricare dal disco il sistema operativo, collocandolo in memoria ram, una volta che il so è stato caricato in memoria ram, il bootstrap passa il controllo al sistema operativo
- Imposta la cpu in maniera tale che esso abbia l'accesso corretto alle operazioni della cpu

## Servizi del sistema operativo
---
