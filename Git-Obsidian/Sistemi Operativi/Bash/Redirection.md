## Ridirezionamento di Stream I/O
### Ridirezionamento dei File Descriptor dei Processi Figli
>[!info] Concetto
> Quando lanciamo uno *script* all'interno di una `bash` il *processo figlio* ottiene una ***copia*** dei [[File Descriptor]] del padre.
>Il padre può decidere, nel momento in cui lancia il processo figlio, di cambiare gli ***stream*** da far usare al figlio
>>[!hint] In tal caso
>>I *file descriptor* passati al figlio saranno gli ***stessi***, ma saranno associati a ***stream diversi***

#### Caratteri di Ridirezionamento
>[!caution] `<`
>Indico che voglio ricevere *input* ***da un file*** che apro in ***lettura***

```bash title:"Ricevere input da File"
program < file_input_name
# Il file [file_input_name] viene aperto in lettura e collegato al file descriptor 0
# Il processo program vedrà come file descriptor 0 (stdin) il file [file_input_name]
```

```bash title:Esempio
while read VAR
do
	echo $VAR
done < file_name
# Legge tutte le righe del file [file_name]
```


>[!abstract] `>`
>Indico che voglio mandare l'*output* ***verso un file***, **eliminando** il vecchio contenuto del file

```bash title:Esempio
echo text_to_write > file_name
cat file_name
# text_to_write
```

###### Specifica
>Senza mettere alcun valore prima del simbolo di ridirezionamento

Viene ***ridirezionato*** lo *standard output* di default ([[File Descriptor]] `0`)
- È possibile specificare tramite *file descriptor* uno specifico *stream*
	- `{bash} program 2> out_error` Ridireziona solamente lo `stderr`

>[!tldr] `>>`
>Indico che voglio mandare l'*output* ***verso un file***, **aggiungendo** nuovi contenuti in coda

```bash title:Esempio
# With the same file from before
echo more_text_to_write > file_name
cat file_name
# text_to_write
# more_text_to_write
```

>[!note] `|`
>Consente di mettere in *esecuzione* ***due processi*** che eseguono in *contemporanea*, collegando lo `stdo` in un processo allo `stdin` dell'altro processo



##### Più Ridirezionamenti
>[!hint] Osservazione
>È Possibile fare più ridirezionamenti in un solo comando

```bash title:Esempio
program < input_file > output_file
```

###### Ridirezionamento di `stderr` e `stdout` in uno stesso File
>[!abstract] Comando
>`{bash}program &> file_output`

#### Here Documents
>[!summary] `<<`
>La *word* che segue il metacarattere `<<` viene utilizzata come *delimitatore finale* dell'***input da passare*** al *comando a sinistra* del metacarattere

```bash title:Esempio
while read A B C; do echo $B;done <<FINE
uno due tre quattro
alfa beta gamma
gatto cane
FINE
echo ciao
# Stampa in output:
# due
# beta
# cane
```

### Auto-Ridirezionamento
>[!example] Ridirezionamento di Propri File Descriptor
>Un processo può decidere di *aprire nuovi file*, *chiudere file aperti* o associare un proprio [[File Descriptor]] ad un ***altro stream***
>>[!question] Come Fare?
>> Il ***ridirezionamento*** di *propri file descriptor* avviene tramite comando `exec`

