## I Servizi del Sistema Operativo
---
>[!question] Che cosa fa il Sistema Operativo?
### Risorse
>[!info] Controllo delle risorse
>Il ***sistema operativo*** prende possesso delle [[18 - Risorse|risorse]] come:
>
>>[!tip] Allocazione
>>Il sistema operativo alloca ai processi:
>>- Il tempo di utilizzo della `CPU`
>>	- Decide a quali processi fare usare la `CPU`
>>		- ***Scheduling***: Meccanismo che si occupa di dare l'uso della `CPU` un po' alla volta a tutti i processi in esecuzione
>>- Memoria dal disco
>
>>[!caution] Contabilizzazione
>>Il ***sistema operativo*** tiene traccia di quanto un processo sta usando risorse per poter dare a tutti i processi le risorse ***equamente***
>
>>[!tldr] Protezione e sicurezza
>>Il *sistema operativo* ha il compito di ***proteggere*** il sistema stesso, l'hardware e gli utenti
>>- Deve conoscere gli utenti per poter sapere se hanno i diritti di ***lettura / scrittura*** dei file

Il sistema operativo ha pieno controllo delle risorse, e le gestisce in maniera equa per tutti i processi

### Comunicazioni
>[!info] Comunicazione intra e inter - computer
>Il sistema operativo deve ***garantire l'integrità delle informazioni*** che arrivano

Informazioni possono essere esterne (tramite *rete*) o *interne*

### Errori
>[!tldr] Rilevamento degli errori
>Il sistema operativo deve essere in grado di rilevare gli ***errori*** che possono verificarsi nella `CPU`
>- E eventualmente una potenziale ***correzione*** per evitare che il sistema venga ***danneggiato*** da file corrotti o errati

### File System

>[!info] Gestione del file system
> Il sistema operativo deve consentire ai programmi e al sistema stesso di ***utilizzare memoria di massa*** e secondaria, e organizzarla in una ***struttura gerarchica di directories e files***
### Input / Output
>[!summary] Gestione delle operazioni di *I/O*
> Il sistema operativo fornisce all'utente i mezzi per effettuare operazioni di ***I/O*** su ***file*** o ***periferica***

### Esecuzione
>[!info] Esecuzione di programmi
 > Il sistema operativo si occupa di ***mettere in esecuzione il processo***, copiandone l'immagine dal programma
