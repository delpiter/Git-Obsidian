---
## Avvio del sistema operativo
---
Controlli di flusso
`for *condizione* do *comandi* done`
`while do done`
`if then elif else`

Espressione condizionale
`[condizione di un file]`
- Permette di verificare delle condizioni attinenti al sistema operativo
	- Es. utente ha i permessi di `rwx`
	- Serve per scrivere script che riescono ad ottenere informazioni legate al file system

Valutazione di espressione matematica
- Valuta solo variabili d'ambiente
`((*istruzione con espressione*))`


### Parametri a riga di comando passati al programma

##### Parameter Expansion
>Esistono variabili particolari che rappresentano gli argomenti passati ad uno script

`$#` -> Contiene il numero di argomenti passati allo script
`$0` il nome del processo in esecuzione (nome dello script)
- `$1` primo argomento
- `$2` secondo argomento
- ...
`$*` tutti gli argomenti passati concatenati e separati da spazio
`$@` come `$*` ma se "protetto" da apici `""` gli argomenti vengono quotati separatamente

Questi parametri non possono essere modificati
Questi parametri sono visti all'interno degli script in esecuzione
