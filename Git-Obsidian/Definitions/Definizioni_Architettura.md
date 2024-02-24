## Il Calcolatore
---
>[!info] Hardware
L'**hardware** è l’insieme dei dispositivi che compongono il calcolatore. Si compone di oggetti tangibili: circuiti integrati, memorie, stampanti, ecc.

>[!info] Software
Il **software** è l’insieme delle istruzioni e delle informazioni necessarie per risolvere i problemi a cui il sistema è preposto. Un insieme di istruzioni, codificate in termini comprensibili a un calcolatore, per risolvere un problema

- Il software **richiede** un apposito hardware per essere eseguito, **viceversa** l’hardware è pressoché inutile se non si dispone di un apposito software che ne sfrutti le potenzialità

- Programmare un calcolatore significa scrivere la sequenza di istruzioni ([[Git-Obsidian/Algoritmi e Strutture Dati/Appunti|Appunti]]) necessaria a risolvere un problema. 
>[!info] Firmware
Il **firmware** è un software integrato in un componente elettronico in grado di **avviare** il componente stesso e di farlo **interagire** con altri componenti.

## Traduzione di Programmi
---
### Compilazione
>[!tip] Definizione
>Il codice viene "inviato" ad un traduttore (*Compilatore/Assemblatore*) che avrà il compito di tradurre il programma in linguaggio macchina-`i` e produce un nuovo programma in un linguaggio macchina più basso
>>[!done] Il compilatore:
>>1. Traduce
>>2. Salva (generalmente un file in linguaggio oggetto: `.obj` o `.o`)
>>3. Codice eseguibile in un secondo momento

### Interpretazione
>[!tip] Definizione
>Il traduttore (o *interprete*) legge il programma in linguaggio macchina-`i`, il programma verrà eseguito direttamente.
>Il compito dell'**interprete** sarà quello di compilare (o "tradurre") riga per riga durante l'esecuzione (**run time**)
>>[!done] I'interprete
>> 1. Traduce man mano che esegue


### Linker
>[!tip] Definizione
>Il linker ha il computo di collegare i moduli e risolvere i riferimenti inter-modulo durante la **compilazione**
>Serve per ottenere una unica sequenza di byte, un unico file eseguibile
>- Su windows genera un unico file `.exe`

### Loader

> [!tip] Definizione
> Carica il programma in memoria e trasforma i riferimenti tra le istruzioni  in indirizzi di memoria
> - "Genera" il programma in esecuzione

