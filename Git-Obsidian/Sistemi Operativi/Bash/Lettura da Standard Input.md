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
