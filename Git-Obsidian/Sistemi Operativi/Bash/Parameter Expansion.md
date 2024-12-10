## Parametri a Riga di Comando passati al Programma
---
>Esistono variabili particolari che rappresentano gli argomenti passati ad uno script

>[!info] Variabili Speciali
>
>>[!caution] `$#`
>>Contiene il *numero di argomenti* passati allo script
>
>>[!abstract] `$0`
>>Contiene il *nome del processo* in esecuzione (nome  dello script)
>
>>[!note] `$1`, `$2`, `...`
>>Contengono rispettivamente il *primo*, *secondo*, ..., *argomento* passato dal comando
>
>>[!example] `$*`
>>Contiene tutti gli *argomenti passati concatenati* e separati da ***spazio***
>
>>[!tldr] `$@`
>>Come `$*` ma se "*protetto*" da apici, gli argomenti vengono quotati separatamente


Questi parametri sono visibili all'interno di un qualsiasi script in esecuzione
- La `shell` di comandi, essendo uno script, contiene queste variabili, ma sono tutte vuote

>[!danger] Questi parametri non possono essere modificati

### Modifiche del Contenuto della variabile
>Le seguenti espansioni ***non vanno a modificare la variabile***, ma mostrano solamente la modifica apportata

Supponiamo di avere la variabile `VAR="[13] qualcosa con [ 0 ] fine"`
>[!info] Rimozione di Suffissi
>`${VAR%%pattern}`
>- Rimuovo il ***più lungo*** *suffisso* che fa match con la stringa originale
>- `{bash} echo ${VAR%%]*}` stampa in output: `[13`
>
>`${VAR%pattern}`
>- Rimuovo il ***più corto*** *suffisso* che fa match con la stringa originale
>- `{bash} echo ${VAR%]*}` stampa in output: `[13] qualcosa con [ 0 `

>[!tldr ] Rimozione di Prefissi
>`${VAR##pattern}`
>- Rimuovo il ***più lungo*** *prefisso* che fa match con la stringa originale
>- `{bash} echo ${VAR##[*}` stampa in output: `0 ] fine`
>
>`${VAR#pattern}`
>- Rimuovo il ***più corto*** *prefisso* che fa match con la stringa originale
>- `{bash} echo ${VAR#[*}` stampa in output: `13] qualcosa con [ 0 ] fine`

>[!note] Sostituzione
>`${VAR/pattern/string}`
>- Cerca nel contenuto di `VAR` la *sottostringa più lunga* che fa match con il pattern fornito (anche con [[Wildcards]]) e lo *sostituisce* con `string`

>[!abstract] Substring
>`{sh} ${VAR:offset:length}`
>- Mostra la ***sottostringa*** lunga `length` che parte dal carattere numero `offset` del contenuto di `VAR`
>
>`${VAR:offset}`
>- Mostra la ***sottostringa*** che parte dal carattere numero `offset` del contenuto di `VAR`