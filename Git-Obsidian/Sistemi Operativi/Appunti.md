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

>[!quote] Ghini
>>[!fail] Errore:
>>_stronzo mi stai parlando in tedesco, che sono finlandese_

Per l'esecuzione dello script, in ogni caso viene creato un nuovo processo figlio (una nuova shell)

 - Lo script viene quasi sempre(\*) eseguito dal processo figlio
 - Quando il processo figlio inizia l'esecuzione, il processo padre ferma la propria esecuzione e si mette in attesa che il processo figlio finisca
 - Quando il processo figlio termina, il padre riprende il controllo
	 - I processi figli sono in grado di restituire un valore intero che indica se l'esecuzione dello script è andata a buon fine o meno
	- Al termine dell'esecuzione l'ambiente "figlio" viene eliminato dalla memoria

 (\*) Una shell può eseguire uno script attraverso la keyword `source` o `.`
 - Scrivendo `source nomescript` o `. nomescript` lo script viene eseguito dalla shell su cui è stato scritto il comando 

>[!question] A cosa serve?

Serve a modificare le variabili della shell mediante uno script
- Poiché lanciando normalmente uno script, modificare le variabili nello script non modifica le variabile della shell chiamante

>[!warning] Per eseguire uno script con il comando `source` non è necessario avere i permessi di esecuzione

Il comando `source`, infatti, non esegue direttamente l'eseguibile, ma lo legge e esegue una dopo l'altra le operazioni all'interno dello script

con il comando source non viene considerata la prima riga:
- `#!/usr/bin/perl` che indica l'interprete da usare per quello script
- Di conseguenza lo script darà errore

Comando `exit number`
- Chiude la shell corrente
- Consente di ritornare un valore dalla chiusura dello script

`var="string" command`, la variabile creata all'interno della nuova shell in esecuzione dello script command è una variabile d'ambiente
- Se la variabile `var` esiste già nella shell corrente, non viene sovra scritta, viene invece creata una nuova variabile, che non tocca quella del padre

### Variabili vuote vs Variabili non esistenti
Variabile vuota:
- `VAR=`
- Ci sono alcune occasioni, dove solamente l'esistenza delle variabili, serve a dare un componente informativo

Per eliminare una variabile:
- `unser variablename`

Variabile che non esiste:
- Una variabile che non esiste  è una variabile che non è mai stata dichiarata


### History Expansion
 La bash mantiene una lista completa di tutti i comandi eseguiti in precedenza
 - Dando a ciascun comando eseguito un identificatore in maniera crescente

Il comando `history` stampa a video tutta la storia dei comandi

È possibile eseguire un comando per tramite del suo indice identificativo
- `!1008`
	- Esegue il comando con l'id `1008`
È possibile eseguire un comando precedentemente eseguito per nome
- `!ca`
	- Esegue il comando che inizia con `ca` più recente

>[!danger] Comandi Potenzialmente Pericolosi

Comando `set`
- Lanciato senza nessun parametro visualizza tutte le variabili della shell
	- Sia locali che d'ambiente
	- Visualizza inoltre le funzioni implementate nella shell
- Lanciato con un parametro
	- Serve a settare o resettare una opzione di comportamento della shell in cui viene eseguito
	- `set +o history` -> disabilito la memorizzazione di nuovi comandi 
	- `set -o history` -> riabilito

`set -a` -> dal momento in cui viene lanciato il comando, creare una variabile nuova, o modificare una vecchia, imposta le variabili direttamente d'ambiente

>[!question] Come creare una variabile locale ora??

`export -n var=hello`, crea una variabile locale (solo se  eseguito dopo il comando `set -a`???)

### Passaggio di argomenti ad un eseguibile
`chomod u+x /home/pinacoteca/example.exe`

La prima parola: `chmod` è il nome dell'***eseguibile*** o argomento di indice 0
Ciascuno degli altri pezzi è un argomento o parametro
- La sequenza di caratteri `u+x` è l'argomento di indice 1
- La sequenza di caratteri `/home/pinacoteca/example.exe` è l'argomento di indice 2
- Si dice che in questo caso il numero di argomenti passati è 2

### Avvio della shell bash
L'interprete bash si comporta in modo diverso in base a quali argomenti gli vengono passati all'avvio
Separati in 3 gruppi

Shell non interattiva
- Shell figlia che esegue script
- All'esecuzione del comando: `./executabl.sh`
	- La bash in realtà esegue il comando:
	- `/bin/bash -c ./executable.sh`
- Lanciata con `-c` passato come argomento
- Non è possibile modificare (personalizzare)

Shell interattiva di login (parametro `-l` o `--login`)
- Interfaccia utente eseguita quando un sistema operativo non ha interfaccia grafica
- Cerca di eseguire i seguenti file:
	- `/etc/profile`
		- Viene eseguito dalla bash tramite source
			- Il comando imposta le variabili di default della shell
	- Uno solo (il primo trovato) tra: `.bash_profile`,`.bash_login`, `-profile`
	- Il file `.bashrc` nella home directory dell'utente (serve per customizzare la shell)
- Chiede uno username e successivamente una password
- Una volta verificato l'utente si apre una shell interattiva
Quando termina esegue il file `.bash_logout`


Shell interattiva non di login
- shell che viene eseguita all'inizio nella finestra del terminale
- Anche questa modificabile tramite il file `.bashrc`

### Brace expansion
Un ordine di brace expansion è una stringa di testo
Sono espansioni della riga costituite da 3 parti e due separatori
- ha una parte iniziale, seguita da una parentesi graffa, seguita da altro testo seguito da parentesi graffa chiusa seguita da altro testo
	- `asdf{asdf}asdf`
- nella parte centrale non sono presenti tab o spazi bianchi
- creata da preambolo e postcritto (prima e dopo le graffe)
- Dentro le graffe, sono presenti più stringhe separate da virgole
	- Ciascuna rappresenta una possibile scelta di stringhe che possono essere aggiunte al preamboo e seguite dal post scritto

Il comando `echo he{asd,dfg,poe}vb
- viene espanso in questa maniera:
	- `echo heasdvb hedfgvb hepoevb`

Possono mancare preambolo o postcritto o entrambi

>[!warning] Non ci possono essere spazi bianchi o tab
>O non viene riconosciuta come brace expansion

si possono proteggere gli spazi "proteggendo" gli spazi con dei backslash: `{aa,bb\ ,cc}`
- Brace expansion valida


È possibile inserire delle variabili nelle brace expansion
- Inserendo le variabili dentro: `$(variablename)`
- Nell'ordine descritto tempo fa
#### Annidamento
È possibile annidare degli ordini di brace expansion dentro ordini di brace expansion

#### Semplificazione
Sequenze expansion
Sintassi
- Elenchi di caratteri
- `echo a{b..e}f`
	- Sarebbe equivalente a:
	- `echo a{b,c,d,e}f`