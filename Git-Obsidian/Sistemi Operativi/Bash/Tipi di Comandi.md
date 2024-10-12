## Comandi Eseguibili
---
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

## Tipologie di Comando
---
>[!info] Comandi
>I ***Comandi propriamente detti*** sono ordini la cui *implementazione* è ***contenuta*** nel file eseguibile della ***shell*** stessa
>- Anche detti "*built-in commands*"
> 
>>[!warning] Non si trovano come file separati nel file system
>
>Sono ordini che diamo all'interprete di comandi e che l'interprete ***esegue***, senza cercare sul disco un eseguibile corrispondente al nome che noi abbiamo dato come ordine
>>[!done] Servizi
>>Sono nomi di servizi che sono ***implementati dall'interprete stesso***
>
>Es: comando `cd` non esiste l'eseguibile del comando, il comando è implementato direttamente all'interno dell'interprete

>[!tldr] Eseguibili
> *Ordini* la cui implementazione è ***contenuta fuori dalla shell***
> Memorizzata in altri file nel *file system*
> >[!cautiom] Ricerca
>> Sono dei file con il nome che digitiamo da tastiera che troviamo su disco
>> - L'*interprete* quando vede che il comando ***non è implementato internamente***, va a cercare l'eseguibile su disco

#### Differenza fondamentale
Un comando è ***sempre presente***, sa sempre come *eseguire* il comando

Un ***eseguibile*** nel file sistem ***non è detto*** che l'interprete sappia come ***rintracciare*** l'eseguibile
- Bisogna mettere l'interprete nelle condizione di ***saper rintracciare*** l'eseguibile