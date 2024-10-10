---
## Avvio del sistema operativo
---
### File nascosti
File i cui nomi incominciano con `.`
- Il file è considerato nascosto
	- Non viene visualizzato se lancio il comando `ls` senza specificare il flag `-a`


S maiuscola nei permessi
- `S` significa che c'è un errore nella configurazione dei permessi 

### Come eseguire da terminale a linea di comando

I comandi built-in possono essere eseguiti semplicemente invocandone il nome:

I file eseguibili (binari o script) devono essere invocati specificandone:
- Il percorso assoluto a partire dalla root
	- `/home/pinacoteca/file.exe`
- Il percorso relativo a partire dalla directory corrente
	- `../pinacoteca/file.exe`
- Solo il nome, a condizione che il file sia contenuto in una directory specificata nella variabile `PATH`

###  Subshell

>Una subshell è una shell (shell figlia) creata da un'altra shell (shell padre)

Eredita una copia di tutte le variabili d'ambiente e i file aperti
- NON eredita le variabili locali del padre

Quando una shell deve eseguire uno script, deve fare un controllo sulla prima riga di comando dello script
- Indica quale interprete di comandi utilizzare
- Se voglio eseguire uno script in un linguaggio diverso è necessario specificare l'interprete da utilizzare

>[!question] Qual è l'interprete che deve essere usato per eseguire lo script?

Prima riga:
> `#!/bin/bash`
- Va inserito il percorso dell'interprete che si vuole utilizzare
- Se non è presente questa riga, viene utilizzato lo stesso interprete in esecuzione sul momento

```bash
#!/usr/bin/perl

echo sono due
ls -al ./
```
Errore:
- _stronzo mi stai parlando in tedesco, che sono finlandese_

Per l'esecuzione dello script, in ogni caso viene creato un nuovo processo figlio

 - Lo script viene eseguito dal processo figlio
 - Quando il processo figlio inizia l'esecuzione, il processo padre ferma la propria esecuzione e si mette in attesa che il processo figlio finisca
 - Quando il processo figlio termina, il padre riprende il controllo
	 - I processi figli sono in grado di restituire un valore intero che indica se l'esecuzione dello script è andata a buon fine o meno



