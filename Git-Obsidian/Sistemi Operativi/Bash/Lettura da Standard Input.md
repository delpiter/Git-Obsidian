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
