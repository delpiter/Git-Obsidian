---
## Avvio del sistema operativo
---
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