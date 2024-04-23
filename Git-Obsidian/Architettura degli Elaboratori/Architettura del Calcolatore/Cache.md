>*La [[Organizzazione della Memoria#Memoria Principale|memoria principale]] costituita da `DRAM` è più lenta della [[La CPU|CPU]], e pertanto la necessitàdi leggere codice e operandi dalla memoria causa un rallentamento rispetto alle prestazioni teoriche della `CPU`*

>[!done] Soluzione
>Una soluzione potrebbeessere quello di utilizzare `SRAM` invece di `DRAM`, molto più ***veloci*** e ***costose***

## La Memoria Cache
---
>[!info] Cache
>La ***cache*** è una piccola memoria `SRAM` inserita fra la *memoria principale* e la `CPU`
>La `CPU` reperisce sempre i dati dalla ***cache***, come se questa potesse contenere tutta l'informazione memorizzabile in `RAM`
>>[!done] *Cache Hit*
>>Qualora la parola desiderata sia *effettivamente presente* in **cache** otteniamo un indiscutibile *vantaggio* in termini di ***tempo di accesso alla memoria***
>
>>[!fail] *Cache Miss*
>>D'altro canto, se la parola non è presente, è necessario trasferirla da `DRAM` a ***cache*** e poi *leggerla*
>>In questo caso il tempo totale è *sostanzialmente maggiore* rispetto alla lettura della `DRAM`

![[CachePosition.png]]
*L'utilizzo di cache è **vantaggioso** solo quando la percentuale di hit è sufficientemente alta*

### Caricamento del Dato
>*Il caricamento di un dato in un sistema dotato di cache è il seguente:*

>[!abstract] *Steps*
>1. Richiedi il dato alla ***cache***
>2. Se il dato ***è presente*** in cache, caricalo subito (***cache hit***)
>3. *Altrimenti*:
>	1. *Leggi* il dato dalla ***memoria***
>	2. *Carica* il nuovo dato in ***cache***, se la *cache* è #piena, applica la politica di rimpiazzamento per caricare il nuovo dato al posto di uno di quelli esistenti

- I valori ***modificati in cache*** in genere non sono riscritti immediatamente in *memoria*
	- Potrebbero dovere essere nuovamente *aggiornati*
	- Vengono riscritti prima del rimpiazzamento (***write-deferred***)
	- ***write-back***, scrive subito il valore cambiato in *memoria*


>[!info] *Linee di Cache*
>La copia di dati tra memoria principale e cache *non avviene per parole singole* ma per blocchi denominati ***linee di cache***
>La dimensione di una ***linea di cache*** varia da $8$ a $512$ *parole*

## Principi della Cache
---
>[!tldr] Principio di Località Spaziale
>Il ***principio di Località Spaziale*** dice che vi è alta probabilità di accedere, entro un *breve intervallo di tempo*, a celle di memoria con ***indirizzo vicino***

>[!tldr] Principio di Località Temporale
>Il ***principio di Località Temporale*** dice che vi è alta probabilità di accedere nuovamente, entro un *breve intervallo di tempo*, ad una cella di memoria alla quale si è ***appena avuto accesso***

## Tecniche di Gestione
---
