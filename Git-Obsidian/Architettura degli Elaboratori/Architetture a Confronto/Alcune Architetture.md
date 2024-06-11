## Intel Core i7
---
>[!abstract] Architettura
>Esternamente si presenta come una `CPU` [[Tipologie di Architetture#CISC|CISC]] a $32 /64$ `BIT` basato sullo stesso ***ISA*** dei modelli precedenti
>Infatti, in disaccordo con i principi [[Tipologie di Architetture#RISC|RISC]]:
>- Le istruzioni sono ***molte e complesse***
>- I registri visibili sono solo 8
>- La ***lunghezza delle istruzioni*** è variabile da $1$ a $17$ `Byte`
>>[!done] Architettura "Interna"
>>All'interno, però, contiene un nucleo `RISC` moderno che fa largo uso di [[Pipelining]] e [[Pipelining#Architetture Superscalari|architetture superscalari]]
>
>Di seguito l'architettura "***Sandy Bridge***", realizzata a partire dal 2011, contiene un numero di core variabili tra 2 e 6

![[Sandy-Bridge.png]]
>*Schema dell'architettura di un singolo core*

>[!info] Memory Subsystem
>Include la [[Cache]] privata $L_{2}$ unificata, dati e istruzioni insieme
>- In caso di *miss*, si interfaccia con la cache $L_{3}$ condivisa dai diversi core

>[!abstract] Front End
>Ha il compito di prelevare le istruzioni dalla cache $L_{1}$ le istruzioni e di decodificarle nell'ordine del programma
>La decodifica scompone ciascuna istruzione `CISC` in una sequenza di micro-operazioni `RISC`, successivamente eseguite dal cuore `RISC` del processore
>>[!Micro-op Cache]
>>Piccola memoria che contiene la decomposizione di una istruzione complessa, nel caso venga usata spesso
>
>>[!example] Predizione di Salto
>>In questo livello fanno parte anche le [[Predizione di Salto|predizioni di salto dinamico/statico]] i cui dettagli non sono noti

>[!info] Out-Of-Order Control
> Le micro operazioni sono trasferite dalla micro-op cache allo schedulatore
>>[!tldr] Scheduler/Renaming
>>Lo scheduler è in grado di ***eseguire le operazioni fuori ordine***
>>Renaming, assegna i registri ***accessibili al programmatore ai registri fisici*** (*molti di più*)
>
>>[!caution] Retirement Unit
>>L'unità di ritiro garantisce che i risultati prodotti siano equivalenti rispetto a un'esecuzione in ordine

![[Corei7DataPath.png]]
>*Una vista semplificata del datapath di un core i7*

### Famiglie Intel x86
>[!info] Linea Core
>`CPU` destinate a computer di fascia medio-alta e workstation
>- *Core i3*, *Core i5*, *Core i7*, *Core i9*

>[!abstract] Linea Xeon
>`CPU` destinate a server di fascia alta, derivate dalla linea core ma con caratteristiche più avanzate, come il supporto per memoria `ECC` e numero di core più alto

>[!caution] Linea Atom
>`CPU` per dispositivi ultra-portatili, come Notebook e schede per sistemi embedded, caratterizzate da piccole dimensioni e consumi molto contenuti

>[!Example] Linea Pentium/Celeron:
>`CPU` destinate a computer di fascia medio-bassa

