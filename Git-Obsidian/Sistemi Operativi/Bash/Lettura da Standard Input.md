>[!note] Sia Tastiera che File
## Read
---
>Uno script può leggere dallo `STDIN` delle sequenze di caratteri usando il comando `read`

>[!comando]
>Il comando `read [var name]` riceve la ***sequenza di caratteri*** digitate da tastiera fino alla ***pressione del tasto invio*** o quando *intercetta la chiusura* dello `STDIN` prima di una andata a capo
>>[!summary] Casi Possibili
>>La `read` restituisce un risultato che indica *come è avvenuta la lettura*
>>- Restituisce $0$ se **non** arriva a ***fine file*** e viene *letto* qualcosa
>>- Restituisce $>0$ se si arriva a ***fine file*** (o viene premuto `ctrl + D`)
>- Il comando *inserisce* dentro la ***variabile specificata*** la suddetta *serie di caratteri*

``` bash
while true ;do 
	read RIGA 
	if (( "$?" != 0 )) 
	then 
		echo “eof reached " 
		break 
	else 
		echo "read \"${RIGA}\" " 
	fi 
done
```

#### Lettura di Multipli Valori
>[!info] Più Variabili
>Se nel comando `read` vengono specificate più di una variabile ***allora***
>il contenuto della variabile `IFS` viene usato per separare la linea letta alla read

>Se eseguo il *comando* `read varA varB varC` 

- E scrivo a tastiera la frase: "***prima seconda terza***"

Le *variabili* assumono valore:
- `varA="prima" varB="seconda" varC="terza"`

>Se invece scrivo a tastiera la frase "***prima seconda terza quarta***"

Le *variabili* assumono valore:
- `varA="prima" varB="seconda" varC=“terza quarta"`

>Se invece scrivo a tastiera la "***prima seconda***":

Le *variabili* assumono valore:
- `varA="prima" varB="seconda" varC=""`

### Apertura di un File
>[!info] Concetto
>Uno *script* può avere necessità di usare dei ***file*** su disco per fare `I/O`
>È possibile *aprire un file* da disco, ottenere un [[File Descriptor|file descriptor]] che lo rappresenta ed ***utilizzare*** quel file descriptor per ***accedere*** al file aperto

All'apertura del file, l'*utente* è in grado di scegliere il ***file descriptor*** (numero) che rappresenterà il *file aperto*
- Se tale file descriptor è già usato **avvengono dei problemi**

>[!note] In alternativa si può ***chiedere al sistema operativo*** di sceglierne uno libero

#### Operatori

>[!caution] Lettura
>>[!info] Utente sceglie il *file descriptor*
>>`{bash} exec n< filePath`
>
>>[!cite] Sistema operativo sceglie il *file descriptor*
>>`{bash} exec {variableName}< filePath`

>[!tldr] Scrittura
>Se il file ***non esiste***, crea il *file*.
>Se il file ***esiste***, viene eliminato il contenuto e inserito il puntatore alla riga corrente alla prima riga del *file*
>>[!info] Utente sceglie il *file descriptor*
>>`{bash} exec n> filePath`
>
>>[!cite] Sistema operativo sceglie il *file descriptor*
>>`{bash} exec {variableName}> filePath`

>[!summary] Aggiunta in Coda
>Se il file ***esiste***, viene inserito il puntatore all'ultima riga scritta.
>- ***Non*** viene eliminato il *contenuto* precedente
>
>>[!info] Utente sceglie il *file descriptor*
>>`{bash} exec n>> filePath`
>
>>[!cite] Sistema operativo sceglie il *file descriptor*
>>`{bash} exec {variableName}>> filePath`

>[!tip] Lettura e Scrittura
>>[!info] Utente sceglie il *file descriptor*
>>`{bash} exec n<> filePath`
>
>>[!cite] Sistema operativo sceglie il *file descriptor*
>>`{bash} exec {variableName}<> filePath`

>[!danger] Vanno assolutamente rispettati gli ***spazi***
>Prima della ***variabile***(`{variableName}`) e dopo i ***simboli*** (`< > >> <<`)

##### Esempio
```bash title:"Lettura da File"
exec {FD}< /home/userName/file.txt
if (( $? == 0 )); then
	while read -u ${FD} stringRead;
	do
		echo "read: ${stringRead}"
	done
fi
```

```bash title:"Scrittura da File"
exec {FD}> /home/userName/file.txt 
for name in pippo pippa pippi ; do 
	echo "insert ${name}" 1>&${FD}
	# redirect from stout (1) to the file indicated by the FD
done
```

### Chiusura del File
>[!info] Chiusura dei File
>Qualunque sia il ***modo di apertura*** con cui ho aperto un *file*, la chiusura di un *file* può essere effettuata utilizzando il comando `{bash}exec` con il ***seguente operatore***
>`{bash}exec {FD}>&-`


