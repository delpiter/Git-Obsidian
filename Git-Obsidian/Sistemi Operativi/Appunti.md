---
## Avvio del sistema operativo
---
## Scheduling
Per rappresentare uno schedule si usano i diagrammi di Gantt

![[Pasted image 20241014150417.png]]

Ogni "linea" rappresenta una risorsa diversa, nel nostro caso sarebbe un doppio processore

Eventi che possono causare un context switch
1. Quando un processo cambia stato
	1. Running -> waiting
	2. Running -> Ready
	3. Waiting -> Ready
2. Quando un processo termina

## Politiche di scheduling
Due tipi di scheduler:
- Preemptive
- Non-Preemtive

>Non-Preemptive (vecchio in culo)
- Quando avviene un context switch solo nel caso in cui il processo termina oppure si mette in attesa di un'altra risorsa
	- Va avanti finchè non è forzato a fermarsi

Pro:
- Non richiede alcuni meccanismi hardware come timer programmabili -> più semplici da progettare

>Preemptive
- Avviene un context switch in qualsiasi condizione
	- Processo termina
	- Processo si mette in attesa di risorsa
	- Il suo quanto di tempo termina
	- ...

Pro:
- Permette di utilizzare al meglio le risorse
#### Criteri di scelta di uno scheduler
3 metriche fondamentali per capire la bontà di una tecnica di scheduling 


Da massimizzare:
Utilizzo della risorsa
- Percentuale di tempo in cui la `CPU` è occupata ad eseguire processi
	- Deve essere massimizzato

Throughput
- Numero di processi completati per unità di tempo
	- Dipende dalla lunghezza dei processi
- Anche esso deve essere massimizzato 

Da minimizzare:
Tempo di turnaround
- Tempo che trascorre dalla creazione di un processo alla sua terminazione


Tempo di attesa
- Tempo trascorso da un processo nella coda ready

Tempo di risposta
- Tempo che intercorre fra la sottomissione di un processo e il tempo di prima risposta

#### Caratteristiche dei processi
Durante l'esecuzione di un processo, la `cpu` alterna periodi di:
- `CPU` burst
- `I/O` burst

I processi caratterizzati da `CPU` burst lunghi si dicono `cPU` bound
in alternativa si dicono `I/O` bound

## Algoritmi
First Come First Served
Shortest-Job First
- Shortest next `cpu` burst first
- Shortest remaining time first
Round Robin

FCFS
ALgoritno che esegue per primo il processo che arriva per primo
- Non preemptive

Implementazione semplice, tramite una struttura dati *coda* (politica FIFO)

Problemi elevati tempi medi di attesa e turnaround
- Processi `CPU` bound ritardano i processi `I/O` bound

Convoy Effect:
- Una serie di processi `I/O` bound si mettono in coda dietro al processo `CPU` bound
	- Mentre i processi `I/O` bound sono in attesa della disponibilità della risorsa che il processo `CPU` bound sta occupando, la ready queue rimane vuota

 SJF
 - Shortest next CPU burst First

La `CPU` viene assegnata al processo ready che ha la minima durata della `CPU` burst successivo
- Non preemptive
- Ottimale rispetto al tempo di attesa
	- Impossibile daimplementare in pratica
	- È solo possibile fornire delle approssimazioni tramite tecniche euristiche

Calcolo approssimato della durata del `CPU` burst

- Basata su media esponenziale dei `CPU` burst precedenti

>Sia $t_{n}$ il tempo dell' $n$-esimo `CPU` burst e $T_{n}$ la corrispondente previsione

$\alpha$ rappresenta il peso: devo dare più peso alla previsione o al tempo effettivo??

$T_{n+1}$ può essere calcolato come segue

$$
T_{n+1}=\alpha t_{n}+(1-\alpha)T_{n}
$$

Una sorta di media pesata fra il valore di tempo del burst previsto e la durata effettiva

- Media esponenziale

$$
T_{n+1}=\sum_{j=0}^n \alpha(1-\alpha)^j\cdot t_{n-j} +(1-\alpha)^{n+1} T_{0}
$$

SJF preemptive e non preemptive
- Non preemptive
	- Una volta il processo più "corto" è in esecuzione continua fino alla terminazione, anche se uno più corto entra nella coda
- Preemptive
	- Il processo in esecuzione può essere messo nella coda ready se arriva un processo con un `CPU` burst più breve di quanto rimane da eseguire al processo corrente
		- Shortest remaining time first


### Laboratorio
> Aprire la macchina virtuale personale

- Desktop
	- Cartella MappaSO.cmd -> Esegui
		- Lo script monta una directory la macchina personale
- Explorer -> questo pc -> Disco SO remoto
	- Cerca la cartella con il proprio nome
	- File: lubuntu 22.04.vmx

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
