## Memoria Principale
---
>[!info] `RAM`
>La `RAM`, ***R***andom ***A***ccess ***M***emory, o *memoria principale* è quella parte del calcolatore preposta a **immagazzinare** i *programmi in esecuzione* e i relativi *dati*
>La [[Le Memorie|memoria]] principale è di tipo ***volatile***

La `RAM` si compone di un ***numero di celle***, ognuna delle quali è in grado di memorizzare una *parte delle informazioni*
- Ogni *cella* è associata ad un ***indirizzo*** che la identifica univocamente

 Tutte le *celle* di una memoria mantengono lo ***stesso numero*** di `BIT`
 - Il numero di `BIT` associato a un indirizzo è detto *word*
 - La dimensione minima è il `BYTE`
 - La dimensione della *word* determina anche le dimensioni dei ***registri*** e delle ***istruzioni***

>[!done] Indirizzamento

Gli indirizzi di memoria sono espressi tramite numeri binari:
- Se un indirizzo ha $m$ `BIT` il numero massimo di celle indirizzabili sarà $2^m$

### Assemblaggio
>*I **chip** di memoria non vengono venduti singolarmente ma sono normalmente organizzati su schede stampate*
>*Ogni scheda contiene generalmente da $8$ a $16$ **chip***

![[Pasted image 20240327115941.png]]

#### Tipi di Memoria Principale
>[!tldr] SIMM
>***S***ingle ***I***nline ***M***emory ***M***odule
>È un tipo di *banco di memoria* dove i ***contatti dorati*** si trovano solo su un lato della scheda

>[!summary] DIMM
>***D***ual ***I***nline ***M***emory ***M***odule
>È un tipo di *banco di memoria* dove i ***contatti dorati*** si trovano su entrambi i lati della scheda
>La velocità dipende dalla ***tipologia di memoria*** (`DDR`, `DDR2`, `DDR3`, `DDR4`, `DDR5`)

>[!tldr] SO-DIMM
>***S***mall ***O***utline ***DIMM***
>Sono ***DIMM*** a dimensioni ridotte usate in genere nei portatili

>[!summary] ECC-DIMM
>***E***rror ***C***orrecting ***C***ode ***DIMM***
>I moduli `ECC-DIMM` prevedono meccanismi di ***correzione di errore***.
>Per motivi di ***risparmio e bassa probabilità di errore***, questi chip non sono presenti su calcolatori ordinari
>>[!question] Probabilità di errore
>>Alcune ricerche hanno dimostrato che, anche se con probabilità ridicola, i ***raggi cosmici*** possono causare errori nei singoli `BIT` delle `RAM`

## Dischi Magnetici
---
>[!info] Hard Disk
>Un ***hard disk*** (***HD***) è un dispositivo ***elettro-meccanico*** per la conservazione di informazioni sotto forma *magnetica*, su supporto rotante a forma di ***piatto***, su cui agiscono delle ***testine*** di *lettura/scrittura*
>[[Le Memorie|Memoria]] di tipo ***persistente*** e ***on line***

![[Pasted image 20240327133131.png]]
### Testina
>[!tldr] La testina di lettura/scrittura
>La ***testina*** di un disco, contenente un induttore, è sospesa sopra la superficie e viene sostenuta da un cuscino ad area

![[Pasted image 20240327133456.png]]

### Scrittura
>[!info] Scrittura
>Quando la corrente **negativa** o **positiva** passa *attraverso la testina*, viene ***magnetizzata*** la superficie appena sotto la testina e le *particelle magnetiche si allineano* verso sinistra o destra a seconda della **polarizzazione della corrente**

### Lettura
>[!info] Lettura
>Quando una testina passa sopra ***un'area magnetizzata***, viene *indotta* una *corrente* **positiva** o **negativa** nella testina, e ciò permette di rileggere i `BIT` memorizzati precedentemente

### Struttura del Disco
>*Il disco rigido è formato da diverse parti, tra cui le principali:*


![[Pasted image 20240327134729.png]]

>[!tldr] Traccia
>La ***traccia*** è una sequenza circolare di `BIT`

>[!tip] Settore
>*Porzione* di traccia di ***dimensione fissa***
>Ogni settore è composto da:
>>[!info] Preambolo
>>Il ***preambolo*** è necessario alla testina per ***sincronizzarsi*** prima della *lettura/scrittura*
>
>>[!example] Dati
>>I ***dati*** sono l'insieme dei `BYTE` memorizzati nel *settore*, normalmente $512$
>
>>[!info] Codice di Correzione Errori
>>Il [[Correzione di Errori|Codice di Correzione Errori]] è utilizzato per individuare e correggere eventuali errori

![[Pasted image 20240327140932.png]]
>[!tldr] Cilindro
>Il ***cilindro*** è l'*insieme delle tracce* in una data posizione radiale
>Il cilindro è un concetto ***virtuale***, non esiste fisicamente un *cilindro*
>>[!question] Perché Cilindro?
>>Quando una testina legge nel disco, *ogni testina* di *ogni piatto* viene impostata alla ***stessa distanza dal centro*** di ogni piatto
>>"*Cilindro*", poiché per leggere un piatto la testina si mette a posto per leggere tutti i dischi a quella stessa distanza, formando una sorta di **cilindro**

Prima di poter leggere o scrivere la suddetta struttura (*tracce*, *settori*) deve ***essere creata***
- Questa operazione viene detta ***formattazione***

### Capacità
>*La capacità di un hard disk è in gran parte definita dalla densità di registrazione*

>[!info] Densità Lineare
>La densità lineare è limitata dalla difficoltà di individuare le variazione del campo magnetico sulla superficie del disco

>[!info] Densità di Area
>La densità del primo hard disk era di circa $2Kbits/in^2$
>Ora si sono superati i $1.3 Tbits/in^2$

### Prestazioni
>*Le prestazioni di un hard disk dipendono da diversi fattori*

>[!tip] Seek Time
>Il ***seek time*** è il tempo necessario per spostare le *testine* sul *cilindro* desiderato
>I *costruttori* del disco forniscono, in genere:
>>[!example] Average Seek
>>`8-10 ms`
>
>>[!done] Track-to-Track
>>`1 ms`
>
>>[!Full Stroke]
>>`15-20 ms`

>[!tip] Latency Time
>La ***latency time*** rappresenta il tempo necessario affinché il settore interessato all'operazione ***passi sotto la testina***.
>Questo fattore è definito dalla velocità di rotazione del disco che varia da $3.600$ a $15.000$ `RPM` (***R***otation ***P***er ***M***inute)

## Solid State Drive
---
>[!info] Descrizione
>Si tratta di dispositivi *completamente elettronici*, normalmente basati su ***memorie flash***, e senza ***nessuna parte in movimento***
>*Ridotti* notevolmente i ***tempi*** di *lettura* e *scrittura*

![[Pasted image 20240328095303.jpg]]

>[!done] Pro

***Tempo di accesso***
- Eliminata la *costante di movimento*
- Tempo di accesso **inferiore** a 100 microsecondi, dalle 30 alle 100 volte più performanti di un hard disk

***Maggiore velocità di trasferimento di dati***
- Oltre i $7 Gb/sec$

***Minore possibilità di rottura e maggiore durata***
- Tasso di rottura inferiore agli *hard disk* (*molto fragili*)

***Rumorosità assente***

***Minori consumi***

***Maggiore capacità***
- Disponibili `SSD` da $100Tb$

>[!fail] Contro

***Maggiore prezzo per*** `BIT`
- Pari a circa *quattro volte* il ***costo*** di un disco tradizionale

***Possibile minore durata dell'unità***
- Il massimo numero di riscritture dello stesso `BIT` può andare da $3.000$ a $100.000$ cicli

## Interfacce
---
>*Esistono diversi tipi di interfacce di trasferimento di dati, implementate sui controller integrati del disco*

### IDE
>[!info] *I*ntegrated *D*rive *E*lectronix
>Interfaccia ormai ***obsoleta***
>È stata la tecnologia *più utilizzata* negli anni $'80$ 
>Il *controller integrato* indirizza i settori indicando:
>- Il numero di *testina* (4 `BIT`)
>- Il *settore* (6 `BIT`)
>- Il *cilindro* (10 `BIT`)
>

>[!done] Spazio Indirizzabile
>`512 BIT`$\times 2^4$ `BIT` $\times 2^6$ `BIT` $\times 2^{10}$ `BIT`


### EIDE
>[!info] *E*xtended *IDE*
>Supporta un diverso *schema di indirizzamento*, `LBA` (***L***ogical ***B***lock ***A***ddressing)
>Numera i **settori** da $0$ a $2^{28}-1$
>Sebbene sia necessario ***rimappare gli indirizzi*** in termini di settori, cilindri e testine, permette di ***aumentare lo spazio indirizzabile*** fino a $128 Gb\implies2^{28}\times2^9$ settori di $512$`BYTE`

#### Evoluzioni EIDE

>[!example] ATA-3
>***A***dvanced ***T***echnology ***A***ttachement

>[!example] ATAPI-4 ATAPI-5 ATAPI-6
>***ATA*** ***P***acket ***I***nterface
>Anche chiamate ***PATA***, ***P***arallel ***ATA***
>Velocità di *trasferimento dati* aumenta gradualmente fra le versioni
>***ATAPI-6***:
>- Indirizzi `LBA` passano a $48$ `BIT`, capacità massima aumentata fino a:
>$$2^{48}\times 2^9$$

>[!example] ATAPI-7
>Meglio nota come ***Serial ATA*** (`SATA`) rappresenta una rottura radicale con il passato
>Si passa da un *trasferimento parallelo* di $16$ o $32$ `BIT` per volta
>- Con cavi piatti a $40/80$ ***fili***
>Al ***trasferimento seriale*** di $1$ `BIT` per volta su un connettore a $7$ ***fili***

### Serial ATA
>[!info] SATA
>Denominato anche `SATA` è una vera e propria rivoluzione in quanto consente:
>- ***Velocità*** superiore fino a $600MB/sec$
>- Diminuzione di ***costo*** per cavi
>- Migliore ***ventilazione*** del `PC` e semplicità di montaggio
>- ***Hot Swap*** delle unità


![[Pasted image 20240329101324.jpg]]
### Interfacce PCI
>[!info] NVMe
>***N***on ***V***olatile ***M***emory ***e***xpress
>Progettate per sfruttare al massimo i vantaggi dei moderni `SSD`
>Velocità teorica di $64 Gbit/sec$ utilizzando 4 canali `PCIe`
>- ***P***eripheral ***C***omponent ***I***nterconnect ***E***xpress
>Possono avere la forma di una ***scheda di memoria*** collegata con un connettore `M.2`
>O sotto forma di un ***disco*** da `2.5` pollici collegato tramite connettore `U.2`

![[image-removebg-preview 3.png]]

### SCSI e SAS
>[!info] SCSI
>***S***mall ***C***omputer ***S***ystem ***I***nterface (pronuncia ***SCASI***)
>Sviluppato *parallelamente* allo standard EIDE, destinato ai ***sistemi di fascia alta*** in ambito ***enterprise***
>La tecnologia di base dei dischi è la stessa.
>- Per utilizzare dischi `SCSI` è generalmente necessario utilizzare un ***controller aggiuntivo***


>[!info] SAS
>***S***erial ***A***ttatched ***S***CSI
>Analogamente al `PATA` anche `SCSI` si è evoluto verso un collegamento punto a punto di tipo seriale
>Non tanto differente in termini di ***prestazioni*** ma in termini di ***affidabilità***

## RAID
---
>*Creato per colmare il divario tra le prestazioni della `CPU` e quello dei dischi*

>[!info] RAID
>***R***edundant ***A***rray of ***I***nexpensive ***D***isk
>Tecnologia di ***virtualizzazione dello storage*** che combina diversi ***dischi fisici*** in uno o più ***unità logiche***
>- Può essere gestito dal `SO` (*Software Raid*) o da un ***controller Hardware***
>- Appare al sistema come un ***disco unico***
>- Aumenta le prestazioni ***distribuendo i dati*** su più dischi a cui il controller accede in **parallelo**
>- Fornisce una modalità di ***backup e correzione di errori***
>- Permette il *funzionamento* anche se una unità ***non è attiva***

### Tipi di RAID
>[!abstract] RAID 0
>***Non Redundant Data Striping***
>Mette assieme 2 o più dischi

![[Pasted image 20240329105526.png]]

>[!abstract] RAID 1
>***Redundant Data Striping***
>Esegue la Copia `BIT` a `BIT` di un disco in un altro

![[Pasted image 20240329105645.png]]

>[!abstract] RAID 2
>***Data Striping at `BIT` Level***

![[Pasted image 20240329105744.png]]

>[!abstract] RAID 3
>***Bit Interleaved Parity***

![[Pasted image 20240329105855.png]]

>[!abstract] RAID 4
>***Block Interleaved Parity***


![[Pasted image 20240329105947.png]]

>[!abstract] RAID 5
>***Block Interleaved Distributed Parity***

![[Pasted image 20240329110047.png]]

## Dischi Ottici
---
### CD
>[!info] Compact Disc
>I `CD` utilizzano un ***principio ottico*** per la memorizzazione persistente di informazioni
>Nati come supporto per la ***memorizzazione di musica***
>>[!abstract] Codifica
>>Le informazioni sono codificate per mezzo di *fori* (***Pit***) di $0.8$ micron di diametro alternati con *zone piane* (***Land***) lungo una ***unica spirale***
>>Un passaggio ***Pit-Land*** o ***Land-Pit*** codifica un $1$
>>L'***assenza di variazioni*** codifica lo $0$

![[Pasted image 20240330162837.png]]

>[!abstract] Lettura
>Le informazioni sono lette tramite un ***raggio laser*** che viene *riflesso* diversamente al passaggio sui ***Pit*** e ***Land***


#### Produzione
I `CD` vengono prodotti utilizzando uno *stampo* ottenuto tramite ***erosione laser***.
- Su questo stampo verrà poi iniettata *resina liquida* che preserva gli incavi corrispondenti ai ***Pit***

Lungo la spirale, i dati sono memorizzati con la ***stessa densità***
- Il `CD` quindi deve ruotare con una ***velocità angolare non costante*** ($530$-$200$ giri al sec)
	- Mantenendo la medesima ***velocità lineare*** ($120cm/sec$) nelle diverse are del `CD`


### CD-ROM
>[!info] CD-Read Only Memory
>Utilizzano la tecnologia dei `CD` per memorizzare dati informatici

>[!fail] Problema: perdita di `BIT` durante la lettura

Al fine di evitare questo problema
- Ogni `BYTE` viene codificato da un ***simbolo*** di $14$ `BIT`
- Nei `BIT` in eccesso viene inserito un ***codice per la correzione dell'errore***
- 