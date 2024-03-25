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
![[Pasted image 20240325224826.png]]
>[!info] Definizione
>Il passaggio di *due operandi* attraverso la `ALU` e la *memorizzazione del risultato* in un nuovo registro viene detto ***ciclo di data path***
>Ogni istruzione [[Il Livello ISA|ISA]] viene eseguita in ***uno o più cicli*** di *data path*
>- Più è ***complessa*** l'operazione ***più cicli*** avrà bisogno per essere *eseguita*

