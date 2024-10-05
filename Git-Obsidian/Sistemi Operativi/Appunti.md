---
## Avvio del sistema operativo
---
Durante l'operazione di bootstrap, vengono eseguite delle istruzioni presenti nella rom che vanno a caricare dal disco il sistema operativo, collocandolo in memoria ram, una volta che il so è stato caricato in memoria ram, il bootstrap passa il controllo al sistema operativo
- Imposta la cpu in maniera tale che esso abbia l'accesso corretto alle operazioni della cpu

## Servizi del sistema operativo
---
>[!question] Che cosa fa il so?

Il so prende possesso delle risorse come
Allocazione
- tempo di utilizzo della cpu
	- Decide a quali processi fare usare la cpu (scheduling, meccanismo che si occupa di dare l'uso della cpu un po alla volta a tutti i processi in esecuzione) si preoccupa di dare tempo di cpu equamente
- disco
- utilizzo di dispositivi

Contabilizzazione
- si tiene traccia di quanto un processo, sta usando risorse per poter dare a tutti i processi le risorse equamente

Protezione e sicurezza
- Deve proteggere il sistema, l'hardware e gli utenti
	-  Deve conoscere gli utenti, per poter sapere se hanno diritti di lettura scrittura dei file


---
Comunicazioni intra e inter-computer
- ci vuole garanzia di integrità delle informazioni che arrivano
---
Rilevamento degli errori che possono verificarsi nella `CPU`
- E eventualmente una potenziale correzione per evitare che il sistema venga danneggiato da file corrotti o errati

---
Gestione del file system
- Consentire ai programmi e al sistema stesso di utilizzare memoria di massa e secondaria, e organizzare la memorai secondaria in una struttura gerarchica di directories e files
---
Gesitone delle operazioni di I/o
- fornisce all'utente i mezzi per effettuare operazioni di i/o su file o periferica

---
 Esecuzione di programmi
 - il so si occupa di mettere in esecuzione il processo, copiandone l'immagine dal programma
 - dando tempo di cpu al programma

---
Interfacce utente
- GUI (graphical user interface)
- CLI (Command line interface)
	- Molto importante: Pro: 
		- comunicazione più veloce fra macchine in remoto (trasferimento di pochi byte, solo messaggi testuali al posto di un itero aggiornamento dell'interfaccia grafica)
		- Automatizzazione delle operazioni
			- Possibilità di scrivere script che eseguono una serie di comandi


## 26-09-2024
---
### CLI
interprete di comandi = shell di comandi
interfaccia che è in grado di recepire dei comandi costituiti da sequenze di caretteri che provengono da tastiera
- L'interprete di comando è un programma che è in grado di legere i caratteri da tastiere
	- per le cli più semplici il comando vengono letti solo quando viene premuto il tasto invio, da qui la sequenza di caratteri viene passato all'interprete di comandi che legge e fa operazioni anche complesse
	- Nelle più moderne, l'interprete legge durante la scrittura, "interpreta" i singoli caratteri facendo delle operazioni che ci facilitano l'utilizzo come il completamento dei nomi dei file

Quando si preme "invio" la sequneza viene ricevuta e la shell analizza il contenuto e decide cosa fare
- Nella riga di comando ci possono essere degli ordini sbagliati
	- La shell non fanulla

2 tipi di comandi
> Comandi propriamente detti
Ordini la cui implementazione è contenuta nel file eseguibile della shell stessa (comandi built-in)
- Non si trovano come file separati nel file system

Sono ordini che diamo agli interprete di comandi e che l'interprete esegue, senza cercare sul disco un eseguibile corrispondente al nome che noi abbiamo dato come ordine
- sono nomi di servizi che sono implementati dall'interprete di comandi stesso
	- Es: comando `cd` non esiste l'eseguibile del comando, il comando è implementato direttamente all'interno dell'interprete

>Eseguibili
Ordini la cui implmentazione è contenuta fuori dalla shell, cioè memorizzata in altri file nel ifle system
Sono dei file con il nome che digitiamo da tastiera che troviamo su disco, l'interprete quando vede che il comando non è implementato internamente, va a cercare l'eseguibile su disco

Differenza fondamentale
- un comando è sempre presente, sa sempre come eseguire il comandpùo
- Un eseguibile nel file sistem non è detto che l'interprete sappia come rintracciare l'eseguibile
	- bisogna mettere l'interprete nelle condizione di saper rintracciare l'eseguibile

shell nei diversi so
- Unix, Linuz: Bash
- Windows: DOS
- Mac: bash

Standard POSIX
- Standard che cerca di uniformare alcune funzionalità che i sistemi operativi mettono a disposizione degli utenti e linguaggi di programmazione

Concetti preliminali:
File system
- Il file system è l'organizzazione del disco rigido che permette di contenere i file e le lori informazioni

lo spazio nel disco rigido è diviso in una o più parti dette partizioni
le partizioni contengono:
- dei contenitori di dati detti files
- dei contenitori di files dietti directories

In windows:
- le partizioni sono viste come logicamente separate e a ciascuna è indicata da una lettera (C, D, E ,...) non c'è il concetto di priorità fra partizioni, non ce n'è una più importante dell'altra sono partizioni "simili"
- Se un file si chiama `file.txt` ed è contenuto in una cartella che si chiama documenti che è contenuta in una cartella che si chiama home contenuta nella partizione C:
	- `file.txt` è univocamente individuabile dal percorso, mediante il qualee partendo dalla partizione C: si arriva al file
		- `C:\home\documenti\file.txt` -> percorso assoluto del file

Il sis op è  in grado di montare una partizione in locale, facendo vedere come se fosse una porzione di disco della macchina, qualcosa che in realtà è montata in remoto

Su linux/mac:
- Esiste una partizione principale : `/`
- Le altre partizioni devono essere logicamente collocate dentro alla partizione principale (in un qualche punto dell'albero della partizione principale)
- Se un file si chiama `file.txt` ed è contenuto in una cartella che si chiama documenti che è contenuta in una cartella che si chiama home contenuta nella partizione `/`
	- `file.txt` è univocamente individuabile dal percorso, mediante il quale partendo dalla partizione `/` si arriva al file
		- `/home/documenti/file.txt` -> percorso assoluto del file
- l'origine del file system è chiamata radice o root

>[!warning] Come capire se un nome in un percorso indica una directory o una partizione?

![[Pasted image 20241005173800.png|350]]
>*Esempio di strutturazione in directories e files delle partizioni di un file system Linux*

#### Uso del terminale Unix

`pwd`
- Comando utilizzato per sapere in quale directory si trova logicamente l'utente
- Visualizza sullo schermo il percorso completo da `/` fino alla directory in cui si trova in quel momento

`cd`
- Comando utilizzato per spostarsi logicamente in una diversa directory, specificata.
- `cd /home/documents`
- `./` -> indica la directory corrente nel percorso relativo
- `../` -> indica la directory padre nel percorso relativo

Nell'immagine di prima, supponendo che siamo nella directory: `mthomas`, per andare nella cartella `bin`:

```bash
cd ../../usr/bin

pwd

/usr/bin
```

`df`
- Comando da delle informazioi su quali sono le partizioni utilizzade dal sistema linux
```bash
> df
Filesystem      1K-blocks      Used Available Use% Mounted on
none              3983968         0   3983968   0% /usr/lib/modules/5.15.153.1-microsoft-standard-WSL2
none              3983968         4   3983964   1% /mnt/wsl
drivers         999143420 115606904 883536516  12% /usr/lib/wsl/drivers
/dev/sdc       1055762868   3062676 998996720   1% /
none              3983968        84   3983884   1% /mnt/wslg
none              3983968         0   3983968   0% /usr/lib/wsl/lib
rootfs            3980552      2208   3978344   1% /init
none              3983968       792   3983176   1% /run
none              3983968         0   3983968   0% /run/lock
none              3983968         0   3983968   0% /run/shm
tmpfs                4096         0      4096   0% /sys/fs/cgroup
```

#### FSH
>Filesystem Hierarchy Standard

Convenzione usata per il layout dei sistemi unix-like
- Definisce una struttura delle directory standard per sistemi operativi unix-like

Obbiettivo
- Sapere dove siano posizionati files/directory e quale sia il loro utilizzo
- Vengono specificate un numero minimo di directory

Directory richieste sotto `/`:

```bash
bin   # Essential command binaries
boot  # Static files of the boot loader
dev   # Device files
etc   # Host-specific system configuration
lib   # Essential shared libraries and kernel modules
media # Mount point for removeable media
mnt   # Mount point for mounting a filesystem temporarily
opt   # Add-on application software packages
sbin  # Essential system binaries
srv   # Data for services provided by this system
tmp   # Temporary files
usr   # Secondary hierarchy
```

#### Caratteri Speciali
Esistono una serie di caratteri che la bash interpreta e in presenza di questi caratteri la bash fa delle operazioni

```bash
> >> <     # redirezione I/O
|          # pipe
* ? […]    # wildcards
`command`  # command substitution (back tick)
;          # esecuzione sequenziale
|| &&      # esecuzione condizionale
(…)        # raggruppamento comandi
&          # esecuzione in background
" " ’ ’    # quoting
#          # commento (tranne un caso speciale)
$          # espansione di variabile
\          # carattere di escape *
<<         # “here document”
```

#### Espansioni
La bash fa una sequenza di operazioni secondo un preciso ordine
- Cerca di interpretare il contenuto del comando scritto facendo delle "espansioni"
Prende il comando originale
- Applica la prima espansione che cambia il contenuto del comando iniziale, modificandolo
- Poi cerca di applicare la seconda espansione al comando modificato

Applica una successione di trasformazioni della riga di comando
- Alla fine esegue il comando modificato

```bash
history expansion 
brace expansion 
tilde expansion 
parameter and variable expansion
arithmetic expansion 
command substitution (effettuata da sinistra verso destra) 
word splitting 
pathname expansion 
quote removal
```

 Le operazioni vengono fatte in questo ordine
 - Non è detto che tutte le espansioni vengano eseguite

## 27-09-2024
---
### Variabile
La shell di comandi permette di usare delle variabili che sono dei simboli dotati di un nome e di un valore
- Il nome è una sequenza di caratteri anche numerici
- Case sensitive
- Il valore è anche esso una sequenza di caratteri compresi caratteri numerici e simboli di punteggiatura

Le variabili possono essere stabilite e modifivate sia dal sistema operativo sia dall'utente che usa quella shell
Alcune variabili dette d'ambiente vengono impostate subito dal sistema operativo non appena viene iniziata l'esecuzione della shell
- Es la variabile PATH

Le variabili possono essere usate quando si scrivono comandi per la shell
- La shell riconosce i nomi delle variabili e cambia il contenuto del comando sostituendo al nome il valore della variabile

Affinchè la shell distingua il nome di una variabile, essa deve essere inserita fra `${name}`

```bash
NUM = fagiano

echo ${NUM}  # Stampa a video: fagiano

echo ${NUM}X # Stampa a video: fagianoX

echo $NUM    # Stampa a video: fagiano

echo $NUMX   # Errore, non viene visualizzato nulla
```

>[!warning] Spaziatura
>Quando si assegna un valore ad una variabile non sono consentiti spazi ne prima ne dopo il simbolo `=`

>Assegnamento con spazio prima del simbolo `=`

```bash 
VARIABLE =content  # Error
VARIABLE = content # Same Error

# Output
VARIABLE: command not found

# Alternativa

ls =content

# Output
ls: cannot acces '=content': No such file or directory
```

La shell cerca di eseguire il comando avente nome `VARAIBILE` passandogli come contenuto `"=content"`

>Assegnamento con spazio dopo il simbolo `=`

```bash
VARIABLE= content
```

La shell cerca di eseguire il comando `content` costruendo per tale comando un nuovo ambiente di esecuzione dove colloca una variabile vuota di nome `VARIABLE`

#### Variabili d'ambiente
variabili che vengono ereditate dai processi figli

 Variabile particolare: `PATH`
 - serve all'interprete per cercare dentro il file system gli eseguibili che l'interprete vorrebbe eseguire ma per cui non è stato specificato il percorso assoluto dell'eseguibile;  dove andare a trovare gli eseguibili da mettere in esecuzione

 - contenuto: `/bin:/sbin:/usr/bin:/usr/local/bin:/home/vittorio`
	 - Sequenza di percorsi assoluti nel file system
	 - Concatenati dentro alla variabile una serie di percorsi
	 - Valore interno definito dal sistema operativo
		 - È possibile modificarlo manualmente

Esecuzione
```bash
wich echo # /usr/bin/echo

echo ciao
ciao

# Alternativa
/usr/bin/echo ciao
ciao
```

#### Variabili locali
variabili che non vengono ereditate dai processi figli

### Comandi eseguibili
Usando l'interfaccia utente a linea di comando possono essere eseguiti:
- Comandi built-in, implementati e inclusi nella shell stessa
- File binari eseguibili, file che contengono codice macchina e si trovano nel file system
- Script, file di testo che contengono una sequenza di nomi di comandi binari e altri script

Per essere eseguito un file binario o uno script deve avere i permessi di esecuzione
- è possibile modificare i permessi di un file o script tramite il comando `chmod`

per vedere i permessi dei file si usa il comando `ls -l`: 
- fammi vedere tutti i file della directory corrente e i relativi permessi


```bash
~/Unibo/OOP/oop-lab02$ ls -l
total 32
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Oct  1 13:26 20-compilation-basics
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Oct  1 13:28 21-compilation-with-packages
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Oct  1 13:30 22-compilation-classpath
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Oct  1 13:33 23-reference-value
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Oct  1 13:36 24-program-arguments
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Oct  1 17:26 25-constructors
drwxr-xr-x 4 pinacoteca pinacoteca 4096 Sep 30 12:49 26-array
drwxr-xr-x 3 pinacoteca pinacoteca 4096 Sep 30 12:19 27-debug
```

escono una serie di 10 caratteri
- Il primo
	- ?
- dal secondo, raggruppati in gruppi di 3:
	- `rwx` o `-`
	- `r` read
	- `w` write
	- `x` execute
	- `-` se è presente un trattino al posto di uno dei caratteri di `rwx` significa che non c'è il permesso corrispondente
- Il primi 3 sono i permessi assegnati al proprietario del file
- I secondi 3 sono i permessi assegnati ai gruppi
- Gli ultimi 3 sono i permessi assegnati a tutti gli altri

#### Utenti e gruppi
Nei sistemi Unix/Linux esistono le astrazioni di utente (user) e gruppo di utenti (group).
- Un utente può corrispondere ad una persona umana oppure essere solo la rappresentazione di una entità usata per indicare chi è che esegue un servizio di sistema

- Un utente (user) è caratterizzato da una stringa username che contiene il nome utente (studente, vic, syslog)
- Un gruppo (group) è caratterizzato da una stringa groupname che contiene il nome del gruppo (staff, admin, )

- Ciascun utente appartiene ad uno o più gruppi.
- Ciascun file (e ciascuna directory) del filesystem appartiene ad un utente (detto proprietario del file,owner) 
	- che normalmente è l'utente che ha creato quel file.
- Ciascun file (e ciascuna directory) è associata ad un gruppo.
- Un utente può tentare di accedere ad un file, chiedendo di leggere o modificare il contenuto di un file oppure di eseguire un file eseguibile, anche se non è il proprietario del file 
- Viene indicato col termine effective user un utente quando cerca di accedere ad un file: il termine permette di distinguere tra chi sta usando il file e chi ne è il proprietario. • Il proprietario di un file stabilisce chi può accedere a quel suo file, configurando i permessi di accesso a quel file. 