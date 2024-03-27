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

