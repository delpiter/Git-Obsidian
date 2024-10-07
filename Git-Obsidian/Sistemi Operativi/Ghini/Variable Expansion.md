## Le Variabili
---
>[!info] Definizione
>La [[Interfaccia Utente#Command Line Interface|shell di comandi]] permette di usare delle ***variabili*** che sono ***simboli*** dotati di un *nome* e di un *valore*
>>[!abstract] Nome
>>Il ***nome*** è una sequenza di caratteri anche numerici
>> *Case sensitive*
>
>>[!tldr] Valore
>> Il ***valore*** è anche esso una sequenza di caratteri compresi caratteri numerici e simboli di punteggiatura

Le variabili possono essere ***stabilite*** e ***modificate*** sia dal *sistema operativo* sia dall'***utente*** che usa la shell

>[!quote] Variabili d'ambiente
>Alcune variabili dette ***d'ambiente***, sono *variabili* che vengono *impostate* dal sistema operativo, non appena viene iniziata l'***esecuzione della shell***
>Sono variabili che vengono ***ereditate*** dai *processi figli*
>>[!example] Esempio
>>La variabile d'ambiente `PATH`
>>- Serve all'interprete per cercare dentro il [[Concetti Preliminali#File System|file system]] gli *eseguibili* che l'interprete *vorrebbe eseguire* ma per cui ***non è stato specificato il percorso***.
>>>[!done] Contenuto
>>>`/bin:/sbin:/usr/bin:/usr/local/bin:/home/vittorio`
>>>- Una sequenza di *percorsi assoluti* nel ***file system***, concatenati dentro alla variabile
>>>- Il valore è definito dal sistema operativo, ma è possibile modificarlo manualmente

>[!quote] Variabili Locali
>Variabili che ***non*** vengono ereditate dai processi figli
#### Esempio Esecuzione
```bash
wich echo # /usr/bin/echo

echo ciao
ciao

# Alternativa
/usr/bin/echo ciao
ciao
```

### Le Variabili nei Comandi
>Le variabili possono essere usate quando si scrivono comandi per la `shell`

La `shell` riconosce i nomi delle variabili e cambia il contenuto del comando ***sostituendo*** al *nome* il *valore* della variabile
- "[[Terminale Unix#Espansioni|Espansione di Variabile]]"

Affinché la `shell` distingua il nome di una *variabile*, essa deve essere inserita come segue:
- `${name}`

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

### Comandi Eseguibili
>[!info] Tipologie di comandi Eseguibili
>Usando l'interfaccia utente a linea di comando, possono essere eseguiti:
>>[!summary] Comandi Built-In
>>Implementati e inclusi nella `shell` stessa
>
>>[!example] File binari e Eseguibili
>>***File*** che contengono *codice macchina* e si trovano nel ***file system***
>
>>[!tip] Script
>>***File*** di testo che contengono una *sequenza* di nomi di ***comandi*** binari e altri ***script***

Per essere ***eseguito*** un file binario o uno script deve avere i [[Utenti e Permessi#Permessi dei File|permessi]] di esecuzione
- È possibile modificare i permessi di un file o script tramite il ***comando*** `chmod`