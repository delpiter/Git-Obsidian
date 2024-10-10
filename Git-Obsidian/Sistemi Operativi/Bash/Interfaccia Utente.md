## Tipi di Interfacce
---
>[!info] Interfacce
> Il sistema operativo può avere 2 tipi diversi di interfaccia
> 
>>[!tldr] Command Line Interface
>>Interfaccia composta da una interfaccia funzionante a ***comandi*** (una serie di *caratteri*)
>>>[!done] Pro
>>> Comunicazione più veloce fra macchine in remoto
>>> - Vengono trasferiti solo pochi `byte`, sotto forma di ***messaggi testuali***, al posto di un intero aggiornamento dell'*interfaccia grafica*
>>>
>>> Automatizzazione delle operazioni
>>> - Possibilità di scrivere ***script*** che eseguono una serie di comandi 
>
>>[!summary] Graphical User Interface
>>Interfaccia che sfrutta ***finestre*** sparate e un ***mouse*** per controllare la posizione dell'utente
>>- Nei sistemi più moderni, la `GUI` implementa un terminale a caratteri

![[GUI.png|400]]
>*Esempio di finestra (window) in una interfaccia grafica*

![[CLI.png]]
>*Esempio di interfaccia a caratteri*


## Command Line Interface
---
>[!info] CLI
>L'interfaccia a caratteri è una interfaccia che è in grado di recepire dei ***comandi*** costituiti da ***sequenze di caratteri***
>>[!tldr] Inteprete
>>L'***interprete*** di *comando* (*shell*) è un programma che è in grado di leggere i caratteri da tastiera
>>- Per le `CLI` più semplici il *comando* viene ***letto*** solo quando viene premuto il tasto *invio*, da qui la sequenza di caratteri viene passato all'*interprete* che ***legge*** e ***esegue*** le operazioni richieste
>>
>>Nelle interfacce più moderne, l'*interprete* legge anche ***durante la scrittura***, *interpretando i singoli caratteri* facendo delle operazioni che ci ***facilitano l'utilizzo*** del terminale:
>>- Completamento dei comandi e dei nomi dei file

Quando si preme "***invio***" la sequneza viene ricevuta e la shell analizza il contenuto e decide cosa fare:
- Nella riga di comando ci possono essere degli ***ordini sbagliati***
	- La shell non fa nulla, spesso stampa a video, l'errore

#### Shell nei diversi Sistemi Operativi
>[!info] Unix-Linux-Mac: ***Bash***

>[!hint] Windows: ***DOS***

#### Standard POSIX
>[!info] Definizione
>*Standard* che cerca di ***uniformare alcune funzionalità*** che i sistemi operativi mettono a disposizione degli utenti e linguaggi di programmazione
### Tipi di Comando
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

