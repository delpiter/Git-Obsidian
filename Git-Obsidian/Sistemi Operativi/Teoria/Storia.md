## Storia dei Sistemi Operativi
---
>Spinta dal progresso tecnologico nel campo dell'hardware

### Generazione 1
>$1945-1955$

>[!info] Valvole e tavole di commutazione

***Ancora non esiste il sistema operativo***
#### Costruzione
Macchine fatte di *valvole*
- Erano in grado di eseguire ***solo calcoli numerici***
	- ***Calcolatori e non elaboratori***

#### Programmi
I programmi erano in linguaggio macchina
- Programmati su *tavole di commutazione*

#### Problemi
> Grossi problemi di affidabilità, provocati da ***guasti frequenti***

>[!fail] Concetto di programmatore come entità separata dal costruttore inesistente

L'operatore doveva:
- ***Caricare*** il programma
- ***Inserire*** i dati
- ***Eseguire*** il programma
### Generazione 2
>$1955-1965$

>[!info] Transistor e sistemi batch

>Introduzione dei transistor

Segue una costruzione di macchine ***sempre più affidabili***

#### Utilizzo
Le macchine iniziano ad essere usate per compiti diversi
- Si crea un mercato

>[!done] Avviene una separazione tra costruttori, operatori e programmatori

#### Programmazione
Introdotti i linguaggi ad "***alto livello***": Assembly, Fortran
- Eseguiti tramite schede *perforate*

>[!abstract] Ciclo di esecuzione

Il ***programmatore*** scrive un programma in un linguaggio ad ***alto livello***
- **Perfora** una serie di ***schede*** con il programma e il suo input
- Consegna le schede ad un operatore

Era compito poi dell'***operatore*** di inserire la scheda e eseguire l'effettivo programma

#### Problema
>[!fail] Molte risorse restavano inutilizzate
### Generazione 3
>$1965-1980$

>[!info] Circuiti integrati, multiprogrammazione e time sharing

Sparisce la figura dell'operatore come "***interfaccia degli utenti***"

#### Programmazione
Programmi scritti con linguaggi ad ***alto livello***:
- `C`, `shell scripting`
- Editor testuali, Compilatori

#### Multiprogrammazione
>[!info] Definizione
>Utilizzazione del processore durante i periodi di `I/O` di un ***job*** (processo) per eseguire un altro ***job***
>>[!example] Caratteristiche tecniche
>>Più job ***contemporaneamente in memoria***
>>Lo ***scheduler*** si preoccupa di alternarli

_Il processore non viene più lasciato inattivo durante le operazioni di `I/O`, solitamente molto lunghe_

#### Time Sharing
>[!info] L'*esecuzione* della `CPU` viene suddivisa in un certo numero di ***quanti temporali***

- Allo scadere di un *quanto* il **job** corrente viene interrotto e l'esecuzione passa ad un altro **job**
- I passaggi (***context switch***) avvengono così frequentemente che più utenti possono interagire con i programmi in esecuzione
### Generazione 4
>$1980-$***oggi***

>[!info] Personal computer

