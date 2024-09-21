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

