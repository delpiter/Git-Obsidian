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