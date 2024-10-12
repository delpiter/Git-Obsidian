---
## Avvio del sistema operativo
---


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