---
## Avvio del sistema operativo
---
## Tilde Expansion

`~` Espansione che riguarda una stringa che è iniziata dal carattere ~
- Espansione che riguarda 5 tipologie di stringhe 
	1. Carattere ~ isolato
	2. Carattere ~ seguito da uno slash
	3. Carattere ~ seguito da slash seguito da altri caratteri
		- Se corrispondono ad una directory, dentro alla directory di un utente, permette di espandere il comando con il percorso assoluto alla directory

`cd ~` -> `cd /home/pinacoteca`
`echo ~/` -> `echo /home/pinacoteca`
`echo ~/Unibo` -> `echo /home/pinacoteca/Unibo`

- tmp
	4. Una parola che inizia con la tilde seguita da nome utente
	5. Una parola che inizia con la tilde seguita da nome utente seguito da slash a cui possono seguire altri caratteri

- In questi casi ~ + nome utente viene sostituita dal percorso assoluto della home directory dell'utente specificato

`echo ~panzieri` -> `echo /home/panzieri`
`echo ~panzieri/test` -> `echo /home/panzieri/test`

Se l'utente non esiste, la bash non esegue alcuna modifica sul comando scritto

## Wildcards `* ? [...]`
### Pathname substitution
Una delle espansioni più importanti

Permette di generare delle stringhe, che possono essere solo percorsi di file / directory

`*`
- Può essere sostituito con una qualsiasi sequenza di caratteri, anche vuota

`?`
- Può essere sostituito con esattamente un carattere

`[...]`
- Può essere sostituito da un solo carattere fra quelli specificati nell'elenco
	- Cosa possono contenere le parentesi, e cosa viene sostituito??
		- `[abc]` può essere sostituito da un solo carattere tra `a`, `b` o `c`
		- `[1-7]` può essere sostituito da una sola cifra compresa tra 1 e 7
		- `[a-g]` può essere sostituito da un solo carattere compreso tra a e g
		- `[[:digit:]]` può essere sostituito da un solo carattere numerico
		- `[[:upper:]]` / `[[:lower:]]` può essere sostituito da un solo carattere maiuscolo / minuscolo

##### Esempio
```bash
echo p* #la bash cerca di sostituire qualunque stringa purche si crei un nome di un file, stampa tutti i file che iniziano con la p

echo p?5 # Stampa tutti i file che iniziano con p, hanno un carattere al centro e finisce con 5
```

### Comandi della bash e eseguibili utili
Comandi
- `pwd` `cd` `mkdir` `ls` `rm` `echo` `cat` ` set` ` ps` `sudo` ` du` ` kill` `bg` `fg` `read` `wc` `killall`

` kill` -> segnale mandato ad un processo per terminare la sua esecuzione

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

Utilità
`man`-> manual
`more` -> vedere a paginate un flusso mandato sullo stdout


pwd mostra directory di lavoro corrente .
cd percorso_directory  cambia la directory di lavoro corrente . 
mkdir percorso_directory crea una nuova directory nel percorso specificato
rmdir percorso_directory elimina la directory specificata, se è vuota
ls-alh percorso stampa informazioni su tutti i files contenuti nel percorso
rm percorso_file elimina il file specificato
echo sequenza di caratteri  visualizza in output la sequenza di caratteri specificata 
cat percorso_file visualizza in output il contenuto del file specificato
env visualizza le variabili ed il loro valore
which nomefileeseguibile visualizza il percorso in cui si trova (solo se nella PATH)  l’eseguibile
mv percorso_file sposta il file specificato in una nuova posizione
ps aux percorso_nuovo  stampa informazioni sui processi in esecuzione 
du percorso_directory visualizza l’occupazione del disco 
kill-9 pid_processo elimina processo avente identificativo pid_processo
killall nome_processo elimina tutti i processi con quel nome nome_processo
bg ripristina un job fermato e messo in sottofondo
fg  porta il job più recente in primo piano
df mostra spazio libero dei filesystem montati
touch percorso_file crea il file specificato se non esiste, oppure ne aggiorna data
more percorso_file mostra il file specificato un poco alla volta mostra
head percorso_file le prime 10 linee del file specificato
tail percorso_file mostra le ultime 10 linee del file specificato
man nomecomando è il manuale, fornisce informazioni sul comando specificato
find cercare dei files
grep cerca tra le righe di file quelle che contengono alcune parole
read nomevariabile legge input da standard input e lo inserisce nella variabile specificata
wc conta il numero di parole o di caratteri di un file
true restituisce exit status 0 (vero)
false restituisce exit status 1 (non vero)

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
