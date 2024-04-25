#To_Be_Continued
## CPU
---
>[!info] ***C***entral ***P***rocess ***U***nit
>Il compito della `CPU` è quello di *eseguire* i programmi *immagazzinati nella memoria* *centrale* leggendo le loro istruzioni ed ***eseguendole in sequenza***

Si può suddividere la `CPU` in 3 ***unità principali***:
### Unità di Controllo
>[!info]
>Legge le istruzioni dalla memoria centrale e ne determina il tipo
>Comparabile al cervello umano, decide e dice cosa fare

### Arithmetic Logic Unit
>[!info]
>Esegue le operazioni necessari all'esecuzione delle istruzioni
>Si occupa di eseguire le operazioni aritmetiche o logiche

### Registri
>[!info]
>La ***più piccola e più veloce*** unità di *memoria* disponibile in un calcolatore, utilizzata per memorizzare i risultati temporanei e le informazioni di controllo necessarie al funzionamento della `ALU`
>Risiedono all'interno della `CPU`

Normalmente i registri hanno tutti le *stesse dimensioni*
- Alcuni vengono utilizzati per ***specifici compiti***
- Altri sono ***general purpose***

>[!tip] Il registro più importante

Il registro più importante è il ***program counter*** (`PC`) che indica la *prossima istruzione da eseguire*

>[!warning] Differenza
>I registri della `CPU` sono differenti rispetto ai [[Registri]] del ***linguaggio assembly***
## Data Path
---
![[DataPath.png]]
>[!info] Definizione
>Il passaggio di *due operandi* attraverso la `ALU` e la *memorizzazione del risultato* in un nuovo registro viene detto ***ciclo di data path***
>Ogni istruzione [[Il Livello ISA|ISA]] viene eseguita in ***uno o più cicli*** di *data path*
>- Più è ***complessa*** l'operazione ***più cicli*** avrà bisogno per essere *eseguita*

### Ciclo di Clock
In architetture non *parallele* il ***ciclo di data path*** corrisponde al ***ciclo di clock***
>[!tldr] Ciclo di Clock
>Il **ciclo di clock** è l'*intervallo di tempo* utilizzato per ***sincronizzare*** le diverse operazioni del processore
>La velocità con cui viene compiuto un ciclo di ***data path*** contribuisce significativamente a determinare la velocità della `CPU`

>[!question] Quante istruzioni al secondo?

*Durata Ciclo di Data Path* $=$ *Durata Ciclo di Clock* $=$ $1/F$
- $F\to$ Frequenza di lavoro della `CPU` 

*Durata istruzione ISA* $=$ $n\times$*Durata ciclo di Data Path*
- $n$ variabile per istruzioni e architetture diverse

### Fetch Decode Execute
>*La `CPU` opera in modo ciclico, ripetendo operazioni fino al termine dell'esecuzione del programma*

>[!abstract] Fetch

***Caricamento***
- Questa operazione ***acquisisce*** dalla memoria il contenuto di un'istruzione del programma

1. *Leggi* l'istruzione seguente dalla memoria e mettila nell'`IR` (***I***nstruction ***R***egister)
2. *Incrementa* il `PC` (***P***rogram ***C***ounter) per indicare l'istruzione seguente

>[!tldr] Decode

***Decodifica***
- Questa operazione ***identifica*** il tipo di operazione da eseguire

3. *Decodifica* l'istruzione appena letta

>[!done] Execute

***Esecuzione***
- Questa operazione ***effettua le operazioni*** corrispondenti all'istruzione decodificata

4. Se l'istruzione *utilizza* degli operandi determina dove si trovano (***memoria***/***registri***)
5. Se necessario *metti* gli operandi in registri della `CPU` 
6. *Esegui* l'istruzione
7. *Salva* il contenuto in un registro
8. Torna al punto 1