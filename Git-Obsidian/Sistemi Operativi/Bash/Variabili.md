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

Per visualizzare le ***variabili d'ambiente***: comando `env`
- Restituisce la lista delle ***variabili d'ambiente***

Per trasformare una ***variabile locale*** in una ***variabile d'ambiente***: comando `export`
- `export variablename`
- `export variablename=value` 
	- Crea direttamente una nuova variabile d'ambiente

>[!quote] Variabili Locali
>Variabili che ***non*** vengono ereditate dai processi figli
>>[!done] Utilizzate per computazioni locali all'interno di uno script

Una *variabile* può essere ***vuota***:
- In alcune occasioni, solamente l'*esistenza della variabile*, serve a dare una ***componete informativa***
##### Eliminazione di una Variabile
>Per eliminare una variabile basta usare il comando `unset`

- `unset variablename`
### Variable Expansion
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

>[[Esecuzione dei File#Variabile e Esecuzione|(\*)]] Assegnamento con spazio dopo il simbolo `=` 

```bash
VARIABLE= content
```

La shell cerca di eseguire il comando `content` costruendo per tale comando un *nuovo ambiente* di esecuzione dove colloca una variabile vuota di nome `VARIABLE`
