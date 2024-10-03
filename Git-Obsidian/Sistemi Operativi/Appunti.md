Ciascuno dei livelli espone una interfaccia per i livelli superiori

Livello privilegio 0, la CPU consente l'esecuzione di tutte le istruzioni macchina messe a disposizione
- livello 1 vengono messe alcune restrizioni
- All'aumentare del livello di privilegio, diminuisce il numero di istruzioni macchina eseguibili
	- All'interno dell'esecuzione di una applicazione utente, il livello di privilegio cambia numerose volte e il controllo dell'esecuzione passa al livello inferiore
	- A fine esecuzione della istruzione "privilegiata" si avvia un meccanismo di ritorno al livello di privilegio precedente


## Distinzione tra modo kernel e modo utente
---	


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
