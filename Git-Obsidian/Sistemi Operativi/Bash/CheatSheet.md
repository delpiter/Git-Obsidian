# Bash Guide & Command Cheatsheet — A dummy-to-dummy summary

> * ✍🏼 **Nicholas Magi**, `nicholas.magi@studio.unibo.it`
> * Corso di **Sistemi Operativi** @ CdL in Ingegneria e Scienze Informatiche, Università di Bologna — Campus di Cesena.
> * Riassunto e schematizzazione delle dispense del prof. **Vittorio Ghini**.
## Nozioni per uso del terminale: *Metacaratteri*

| METACARATTERI | SIGNIFICATO                                            |
| ------------- | ------------------------------------------------------ |
| > >> <        | redirezione I/O                                        |
| \|            | pipe                                                   |
| * ? [...]     | wildcards                                              |
| 'command'     | command substitution (use **backticks**)               |
| ;             | esecuzione **sequenziale** - **separatore di comandi** |
| \|\| &&       | esecuzione **condizionale**                            |
| (...)         | raggruppamento comandi                                 |
| &             | esecuzione in **background**                           |
| " " ' '       | quoting                                                |
| #             | commento                                               |
| $             | espansione di variabile                                |
| \             | carattere di escape *                                  |
| <<            | "here document"                                        |

---
## Nozioni per uso del terminale: *Espansioni*

In ordine di effettuazione

| ESPANSIONE                              | ESEMPIO           |
| --------------------------------------- | ----------------- |
| **1) history expansion**                | !123              |
| **2) brace expansion**                  | a{damn,czk,bubu}e |
| **3) tilde expansion**                  | ~/nomedirectory   |
| **4) parameter and variable expansion** | $1 $? $! ${var}   |
| **5) arithmetic expansion**             | $(())             |
| **6) command substitution** LTR         | $()               |
| **7) word spitting**                    |                   |
| **8) pathname expansion**               | * ? [...]         |
| **9) quote removal**                    | quoting           |

---
## Nozioni per uso del terminale: *Variabili*

| ESEMPIO          | SIGNIFICATO                                                                                                                   |
| ---------------- | ----------------------------------------------------------------------------------------------------------------------------- |
| `MYVAR=PAROLA`   | `MYVAR` ha valore `PAROLA`;  **unico modo di assegnare un valore ad una variabile**, non mettere spazi prima/dopo o in mezzo! |
| `echo ${MYVAR}`  | stampo il valore di `MYVAR`, quindi `PAROLA`.                                                                                 |
| `echo ${MYVAR}x` | stampo il valore di `MYVAR` seguito dal carattere `x`, quindi visualizzerò `PAROLAx`.                                         |
| `echo $MYVAR`    | stampo il valore di `MYVAR`, quindi `PAROLA`.                                                                                 |
| `echo $MYVARx`   | la shell non è in grado di trovare una variabile `MYVARx`, quindi stampa **stringa vuota**.                                   |
| `echo $MYVAR x`  | la shell individua correttamente la variabile `MYVAR`, quindi visualizzerà `PAROLA x`.                                        |
### Variabili note: PATH

`PATH` è una variabile d'ambiente che contiene i percorsi assoluti di alcuni eseguibili utilizzati molto spesso. 

>[!info]
>Esempio di un possibile valore di path: `/bin:/sbin:/usr/bin:/usr/local/bin:/home/nickolausen`

### Riferimenti indiretti a variabili

Operatore **!**: 
- se `IDX=1`, `${!IDX} == $1`;
- se `IDX=2`, `${!IDX} == $2`;
- se `IDX=3`, `${!IDX} == $3`;
- *ecc...*

---
## Nozioni per uso del terminale: *Permessi di file e directory*

Ogni file appartiene ad un utente e ad un gruppo di cui l'utente fa parte: per cambiare owner, usare

```bash
chown <nuovoproprietario> <nomefile> 
```

I permessi di un file sono identificati dai seguenti codici **letterali** e **ottali**, divisi nelle 3 categorie assegnabili: USER, GROUP e OTHERS.

<table>
    <tbody>
		<tr>
			<td colspan=3>USER</td>
			<td colspan=3>GROUP</td>
			<td colspan=3>OTHERS</td>
		</tr>
        <tr>
            <td>R</td>
            <td>W</td>
            <td>X</td>
            <td>R</td>
            <td>W</td>
            <td>X</td>
            <td>R</td>
            <td>W</td>
            <td>X</td>
        </tr>
        <tr>
            <td>4</td>
            <td>2</td>
            <td>1</td>
            <td>4</td>
            <td>2</td>
            <td>1</td>
            <td>4</td>
            <td>2</td>
            <td>1</td>
        </tr>
    </tbody>
</table>

Esempio di assegnazione contemporanea di più permessi **mediante formato numerico**:

```bash
chmod 764 ./miofile.txt
```

Dove:
- 7 = 4 (lettura) + 2 (scrittura) + 1 (esecuzione) per livello **USER**;
- 6 = 4 (lettura) + 2 (scrittura) per livello **GROUP**;
- 4 (lettura) per **OTHERS**;

---
## Nozioni per uso del terminale: *Wildcards*

* `*` -> sostituito con una **qualunque stringa di caratteri**;
* `?` -> sostituito con un **qualunque carattere**;
* `[`*`elenco`*`]` -> sostituito con un qualunque carattere specificato in *elenco*;

### Wildcard *elenco*

| WILDCARD      | SOSTITUZIONE                                                                  |
| ------------- | ----------------------------------------------------------------------------- |
| `[[:digit:]]` | una sola cifra, 0-9                                                           |
| `[[:upper:]]` | un solo carattere **MAIUSCOLO**                                               |
| `[[:lower:]]` | un solo carattere **minuscolo**                                               |
| `[c-f]`       | un solo carattere compreso tra 'c' ed 'f'; *in questo caso, {c, d, e, f}*     |
| `[1-7]`       | un solo carattere compreso tra 1 e 7; *in questo caso, {1, 2, 3, 4, 5, 6, 7}* |
| `[abk]`       | un solo carattere tra 'a', 'b' o 'k'                                          |

---
## Nozioni per uso del terminale: *Parameter Expansion*

Siamo sulla bash, chiamiamo il nostro script passandogli qualche argomento:

```bash
./faiqualcosa.sh argo1 mamma2 soreta4
```

**Dentro a `faiqualcosa.sh` possiamo accedere a diverse informazioni identificate come:**
* `$#`: numero di argomenti ricevuti (*nell'esempio, **3***);
* `$0`: nome del processo in esecuzione (*nell'esempio, **`./faiqualcosa.sh`***)
* `$1` - primo argomento, `$2` - secondo argomento... (*nell'esempio, $1 = `argo1`, $2 = `mamma2`, $3 = `soreta4`*)
* `$*`: tutti gli argomenti ricevuti, concatenati e separati da spazi bianchi (*nell'esempio, `argo1 mamma2 soreta4`*)
* `$@`: come per `$*`, ma gli argomenti sono quotati separatamente (*nell'esempio, `"argo1" "mamma2" "soreta4"`*)

In particolare:

```bash
$* == $@ ---> $1 $2 $3 ... $n

# Se quoto le due variabili, ottengo:
"$*" ---> "$1 $2 $3 ... $n"
"$@" ---> "$1" "$2" "$3" ... "$n"
```

---
## Nozioni per uso del terminale: *Valutazione Aritmetica*

**TUTTA LA RIGA** — Assegno alla variabile `NUM` il risultato di `3+2`:

```bash
(( NUM=3+2 ))
```

>[!warning]
> Non usare **$** prima dell'espressione!

**PARTE DI RIGA** — faccio riferimento, per esempio, ad una variabile `PIPPO5`

```bash
echo PIPPO$((3+2))
```

Le espressioni aritmetiche possono contenere:
- ✅ operatori aritmetici (+, -, \*, /, %)
- ✅ assegnamenti
- ✅ parentesi tonde per modificare la precedenza dei calcoli

> [!info]
> Le espressioni aritmetiche possono essere usate anche come condizione di `while` e `if`. 

---
### Nozioni per uso terminale: *Espressioni condizionali*

### Valori di verità

`true` = exit status 0
`false` = exit status !0

### Operatori logici

NOT: `!`
AND: `&&`, `-a`
OR: `||`, `-o`

### Versioni

> [!warning]
In nessuna versione è supportato:
> - ❌ **WORD SPLITTING**
> - ❌ **BRACE EXPANSION**
> - ❌ **PATHNAME EXPANSION**
> - ❌ **INSERIMENTO COMANDI** (ad eccezione della *command subsitution* con \`\` per generare **operandi**, non operatori!)

1. Con doppie parentesi quadre **\[\[ *`condiz`* \]\]** — *enhanced brackets* 
- ✅ SI a tutte le versioni di operatori logici
- ✅ SI a composizione di espressioni mediante parentesi
- ✅ SI ad andata a capo con carattere **backslash** ( \\ )

2. Con singole parentesi quadre **\[ *`condiz`* \]** — *single brackets*  o mediante istruzione `test`: `test` *`condiz`*
- ❌ NO versioni degli operatori logici C-like — `&&` e `||`
- ❌ NO composizione di espressioni mediante parentesi
- ❌ NO ad andata a capo con carattere **backslash** ( \\ )

### Operatori utili

#### Su FILES

| OPZIONE           | SPIEGAZIONE                                                                                                               |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------- |
| `-d file`         | True if `file` _exists and is a directory_.                                                                               |
| `-e file`         | True if `file` *exists*.                                                                                                  |
| `-f file`         | True if `file` *exists and is a regular file*.                                                                            |
| `-h file`         | True if `file` *exists and is a symbolic link*.                                                                           |
| `-r file`         | True if `file` *exists and is readable*.                                                                                  |
| `-s file`         | True if `file` *exists and has a size greater than zero*.                                                                 |
| `-t fd`           | True if *file* *descriptor `fd` is open and refers to a terminal*.                                                        |
| `-w file`         | True if `file` *exists and is writable*.                                                                                  |
| `-x file`         | True if `file` *exists and is executable*.                                                                                |
| `-O file`         | True if `file` *exists and is owned by the effective user id*.                                                            |
| `-G file`         | True if `file` *exists and is owned by the effective group id*.                                                           |
| `file1 -nt file2` | True if *`file1`* *is newer (according to modification date) than `file2`,<br>or if `file1` exists and `file2` does not*. |
| `file1 -ot file2` | True if *`file1`* *is older (according to modification date) than `file2`,<br>or if `file2` exists and `file1` does not*. |
#### Su STRINGHE

| OPZIONE                                                          | SPIEGAZIONE                                                   |
| ---------------------------------------------------------------- | ------------------------------------------------------------- |
| `-z string`                                                      | True if *the length of* `string` *is zero*.                   |
| `-n string`                                                      | True if *the length of* `string` *is non-zero*.               |
| `string1 == string2`, `string1 = string2`, `string1 -eq string2` | True if *the strings are equal*.                              |
| `string1 != string2`, `string1 -ne string2`                      | True if *the strings are not equal*.                          |
| `string1 < string2`, `string1 -lt string2`                       | True if *`string1` sorts before `string2` lexicographically.* |
| `string1 > string2`, `string1 -gt string2`                       | True if *`string1` sorts after `string2` lexicographically*.  
>[!info]
>Esistono anche le varianti `le` (***l**ess or **e**qual to*) e `ge` (***g**reater or **e**qual to*).


---
## Nozioni per uso del terminale: *Liste di comandi*

In una command line posso scrivere:

1. Un semplice comando

```bash
cd ./mydir
./myscript.sh argument1
```

2. Un'espressione valutata aritmeticamente

```bash
(( VAR=(5+4)*(${VAR}-1)))
```

3. Una sequenza di comandi connessi da | (*pipe*)

```bash
cat $FILE | grep thisword
```

4. Una sequenza di comandi condizionali, in particolare

**4.1.** Eseguo un comando `B` **se e solo se** il comando `A` è andato a buon fine (exit status == 0); 
\[*per esempio: lancio l'eseguibile `myscript.exe` SE E SOLO SE la sua compilazione è andata a buon fine*\]

```bash
gcc myscript.c && ./myscript.exe
```

**4.2** Eseguo un comando `B` **se e solo se** il comando `A` è terminato con un errore (exit status != 0);
\[*per esempio: creo la cartella `mysecretfiles` SE E SOLO SE provando ad entrarci non ha avuto successo*\]

```bash
cd ./mysecretfiles || mkdir mysecretfiles
```

5. Un raggruppamento di comandi

```bash
( cat file1.txt ; cat file2.txt )
```

6. Un'espressione condizionale

```bash
[[ -e file.txt && $1 -gt 13 ]]
```

>[!info]
>L'**exit status di una lista di comandi** corrisponde all'exit status dell'**ultimo comando eseguito**!

---
## Nozioni per uso del terminale: *Compound Commands*

### Cicli — costrutto iterazione

1. Equivalente di un `foreach`

```bash
for FILE in `ls ./Documents` ; do echo $FILE ; done
```

2. Equivalente di un `for`

```bash
for ((IDX=1;IDX<=$#;IDX=IDX+1)) ; do echo ${!IDX} ; done
```

\[*nell'esempio: stampo a video tutti gli argomenti ricevuti dallo script in esecuzione*\]

3. Costrutto `while`

```bash
while read ROW ; do 
	echo "Ho letto $ROW"
done
```

**N.B.:** Posso comporre anche in diverso modo le condizioni di un ciclo, ad esempio:

```bash
IDX=1
while read ROW ; [[ $? == 0 && $IDX -leq 10 ]] ; do 
	echo "Idx:${IDX}\t${ROW}"
	((IDX=$IDX+1))
done 
```

\[*nell'esempio: leggo al massimo 10 righe da `stdin`*\]
### If — costrutto selezione

```bash
FILE=./appunti.txt
if [[ -e $FILE ]] ; then
	echo "${FILE} esiste!"
fi
```

---
## Nozioni per uso del terminale: *Command substitution*

Utilizzo dei **backticks *(o backquotes)*** (\`\`): cattura l'output di un programma - utilizzato per memorizzare i risultati di uno script in una variabile.

```bash
OUT=`.\printnumber.sh`
echo "Catturato l'output $OUT"
```

Utilizzo di **double quotes** (""):
- ❌ NO **;** come separatore tra comandi
- ❌ NO sostituzione wildcards
- ✅ SI visualizzazione contenuto variabili
- ✅ SI esecuzione comandi (se racchiusi da \`\`)

```bash
echo "Dear $USER today is `date`"

stdout: Dear nickolausen today is Fri Dec 13 11:20:55 CET 2024
```

Utilizzo di **single quotes** (''):
- ❌ NO **;** come separatore tra comandi
- ❌ NO sostituzione wildcards
- ❌ NO visualizzazione contenuto variabili
- ❌ NO esecuzione comandi (anche se racchiusi da \`\`)

```bash
echo 'Dear $USER today is `date`'
stdout: Dear $USER today is `date`
```

---
## Nozioni per uso del terminale: *Ridirezionamenti di Stream I/O*

| RIDIREZIONAMENTO | SIGNIFICATO                                                                          |
| ---------------- | ------------------------------------------------------------------------------------ |
| <                | riceve input da file.                                                                |
| >                | manda `stdout` verso un file, **eliminando il vecchio contenuto del file**.          |
| >>               | manda `stdout` verso un file, **aggiungendo in coda al vecchio contenuto del file**. |
| \|               | manda `stdout` del primo comando come `stdin` del secondo.                           |
>[!warning] Ricorda
> Per terminare input da tastiera: **Ctrl + D**

- Ridirezionamento di **input** e **output** possono essere fatti **contemporaneamente**:

```bash
./myscript.sh < ./input.txt > ./output.txt

# oppure, analogamente:
./myscript.sh > ./output.txt < ./input.txt
```

- Ridirezionamento di `stdout` e `stderr` possono essere fatti **contemporaneamente**:

```bash
./myscript.sh &> ./out.txt
```

- Ridirezionamento di `stdout` e `stderr` possono essere fatti in un colpo solo su due file diversi:

```bash
./myscript.sh 2> ./error.txt > ./output.txt
```

- È possibile ridirigere uno stream `N` sullo stream `M` tramite il comando:

```bash
N>&M
```

- È possibile ridirigere contemporaneamente `stderr` e `stdout` di un programma `program1` sullo `stdin` di un programma `program2` tramite pipe:

```bash
./program1.sh |& ./program2.sh
```

---
## Cheatsheet comandi

### Generics

| ESEMPIO                | SIGNIFICATO                                                                                                                                                                                                                                                                                     |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `source ./myscript.sh` | Esegue `myscript.sh` **senza creare una subshell dedicata**. Le variabili create dentro `myscript.sh` sono visibili anche dalla **shell chiamante**. Equivale a  `. ./myscript.sh`.                                                                                                             |
| `unset MYVAR`          | Elimino `MYVAR`, che sia vuota oppure no.                                                                                                                                                                                                                                                       |
| `history`              | Mostra sul terminale lo storico dei comandi eseguiti, associando a ciascuno un numero **immutabile** che **lo identifica**.                                                                                                                                                                     |
| `!181`                 | Lancio il comando identificato dal numero **181** (*guarda history*).                                                                                                                                                                                                                           |
| `set`                  | Lanciato senza parametri, mostra tutte le variabili (locali e d'ambiente) della shell corrente e tutte le funzioni implementate.                                                                                                                                                                |
| `set -a`               | Specifica che tutte le variabili create da quel momento in poi verranno rese d'ambiente, ereditate quindi dalle shell figlie. Comportamento contrario: `set +a`. **N.B.**: Se voglio dichiarare una variabile locale dopo aver eseguito `set -a`, allora utilizzo il comando `export -n MYVAR`. |
| `set +o history`       | Disabilita la memorizzazione nella **history** di ulteriori comandi eseguiti. Comportamento contrario: `set -o history`.                                                                                                                                                                        |
| `pwd`                  | "*Print Working Directory*": visualizza il percorso corrente.                                                                                                                                                                                                                                   |
| `cd mydir`             | "*Change directory*", abbreviativo di `chdir`, naviga nella cartella `mydir`.                                                                                                                                                                                                                   |
| `mkdir nuovadir`       | "*Make directory*", crea una nuova cartella `nuovadir`.                                                                                                                                                                                                                                         |
| `rmdir todelete`       | "*Remove directory*", elimina `todelete` **SOLO SE QUESTA È VUOTA**. Equivalentemente (e senza condizioni) si può optare per `rm -rf todelete` ("*remove -recursive -forced `todelete`*")                                                                                                       |
| `echo MSG`             | Stampa in stdout `MSG`. Se specificato `-n`, non mette il carattere `\n` a fine messaggio (utile per la stampa nei file).                                                                                                                                                                       |
| `cat myfile.txt`       | Stampa in stdout il contenuto del file `myfile.txt`.                                                                                                                                                                                                                                            |
| `env`                  | Visualizza in stdout tutte le variabili d'ambiente.                                                                                                                                                                                                                                             |
| `which python`         | Visualizza il percorso dell'eseguibile `python`.                                                                                                                                                                                                                                                |
| `mv src dst`           | "*Move*", sposta il file `src` in `dst`. Spesso utilizzato per **rinominare files/directories**.                                                                                                                                                                                                |
| `ps aux`               | Stampa informazioni sui processi in esecuzione.                                                                                                                                                                                                                                                 |
| `du mydir`             | "*Disk Usage*": stampa l'utilizzo del disco della cartella `mydir`.                                                                                                                                                                                                                             |
| `kill -9 PID`          | Termina il processo con ID `PID`.                                                                                                                                                                                                                                                               |
| `killall nomeProc`     | Elimina tutti i processi di nome `nomeProc`.                                                                                                                                                                                                                                                    |
| `bg`                   | "*Background*": manda il job corrente in background.                                                                                                                                                                                                                                            |
| `fg`                   | "*Foreground*": ripristina il job più recente in primo piano.                                                                                                                                                                                                                                   |
| `df`                   | "*Disk free*": mostra spazio libero dei filesystem montati.                                                                                                                                                                                                                                     |
| `touch newfile.txt`    | Crea un file `newfile.txt`.                                                                                                                                                                                                                                                                     |
| `more myfile.txt`      | Mostra poco alla volta il contenuto di `myfile.txt`                                                                                                                                                                                                                                             |
| `man grep`             | Mostra la documentazione del comando `grep` (*preso come esempio*).                                                                                                                                                                                                                             |
| `true`                 | Restituisce exit status 0 (vero).                                                                                                                                                                                                                                                               |
| `false`                | Restituisce exit status 1 (falso).                                                                                                                                                                                                                                                              |

### Lettura & gestione file descriptor

#### Visualizzare i file descriptor associati ad un processo

Ricordiamo che in `/proc/` esiste una subdirectory per ogni processo in esecuzione; posso riferirmi alla subdirectory del processo corrente con `/proc/$$` (`$$` = **PID del processo corrente**).

> [!success] I file descriptor associati ad un processo sono collocati nella cartella `/proc/$$/fd/`

#### `read`

```bash
read RIGA
```

Di default, legge il contenuto in `stdin` e lo memorizza in `RIGA`; se vengono specificate più variabili, il contenuto letto viene spezzato in più parole - ciascuna "incastrata" nella variabile corrispondente (*prima parola $\rightarrow$ prima variabile, seconda parola $\rightarrow$ seconda variabile ecc...*). Nel caso in cui vengono dichiarate meno variabili rispetto alle parole da leggere, **l'ultima variabile contiene il testo mancante**

| OPZIONI UTILI |                                                                                     |
| ------------- | ----------------------------------------------------------------------------------- |
| `-u $FD`      | specifica il file descriptor `FD` da cui leggere.                                   |
| `-N 4`        | legge esattamente `4` caratteri da `stdin`.                                         |
| `-r`          | il carattere **backslash** ( \ ) non viene interpretato come interruttore di linea. |
#### `exec`

Ridireziona un file descriptor su un altro.

```bash
bash-3.2$ exec > file
bash-3.2$ date
bash-3.2$ exit
bash-3.2$ cat file
Thu 18 Sep 2014 23:56:25 CEST
```

Nell'esempio, ridireziona qualsiasi messaggio stampato su `stdout` all'interno di `file` fino al comando `exit`. Può essere utilizzato in diverse modalità:

| MODO APERTURA | Utente sceglie il numero associabile al file descriptor (`n`: numero identificativo del file descriptor) | Sistema sceglie file descriptor libero |
| ------------- | -------------------------------------------------------------------------------------------------------- | -------------------------------------- |
| Read-only     | `exec n< ./myfile.txt`                                                                                   | `exec {MYVAR}< ./myfile.txt`           |
| Write-only    | `exec n> ./myfile.txt`                                                                                   | `exec {MYVAR}> ./myfile.txt`           |
| Append        | `exec n>> ./myfile.txt`                                                                                  | `exec {MYVAR}>> ./myfile.txt`          |
| Read&Write    | `exec n<> ./myfile.txt`                                                                                  | `exec {MYVAR}<> ./myfile.txt`          |

>[!info] Ricorda!
> Bash assegna ad alcuni numeri dei file descriptor di **default**:
>- `0` $\rightarrow$ `stdin`
>- `1` $\rightarrow$ `stdout`
>- `2` $\rightarrow$ `stderr`

>[!warning]
>Qualunque sia la modalità di apertura di un file descriptor, questo deve essere chiuso con il comando:

```bash
exec n>&- # n = identificativo del file descriptor in questione

# oppure, se aperto tramite variabile
exec {MYVAR}>&-
```