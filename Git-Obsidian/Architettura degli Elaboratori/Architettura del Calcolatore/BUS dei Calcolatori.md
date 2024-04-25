## BUS
---
>[!info] Definizione
>Un `BUS` è un ***collegamento elettrico*** comunemente *multi-linea* comune fra più dispositivi
>Ci sono $2$ tipi di `BUS`
>>[!abstract] Interni alla [[La CPU|CPU]]
>>Molto veloci, utilizzati per trasportare i dati dai registri alla [[Arithmetic Logic Unit|ALU]].
>>I *protocolli di funzionamento* di questi `BUS` sono solitamente ***tenuti segreti*** dai produttori dei chip
>
>>[!tldr] Esterni alla `CPU`
>>Utilizzati per collegare la `CPU` alla [[Organizzazione della Memoria#Memoria Principale|memoria principale]] e alle *periferiche* come, [[Schede Grafiche|GPU]] e altre [[Le Periferiche|periferiche]]

- Un *`BUS` controller* è necessario per interconnettere tra loro 2 diversi `BUS` "***esterni***"
![[Internal&External_BUS.png]]

>[!warning] `BUS` Esterni

I `BUS` esterni, in particolare quelli che si devono interfacciare con periferiche di terze parti
- Devono attenersi ad uno schema ben preciso denominato ***protocollo del `BUS`***
- Devono essere inoltre perfettamente specificate le ***caratteristiche meccaniche ed elettriche per l'interfacciamento***

### Master e Slave
 
>[!hint] Master
>Si dice ***master*** (o *attivo*) il dispositivo che può *iniziare un trasferimento*

>[!caution] Slave
>Si dice ***slave*** (o *passivo*) il dispositivo che *rimane in attesa di richieste*

- Alcuni esempi di operazioni svolte da ***master e slave***

![[Master-Slave.png]]

### Larghezza del BUS
>[!info] Descrizione
>La ***larghezza del `BUS`*** è uno dei parametri più importanti per la progettazione di un `BUS`
>Indica il ***numero di linee elettriche*** all'interno di un `BUS`

![[BUS_Width.png]]
- *Evoluzione del `BUS` delle prime `CPU` per rimanere retrocompatibile*

### BUS Sincroni e Asincroni
>*I `BUS` possono essere* ***sincroni e asincroni***

>[!hint] Sincroni
>Un `BUS` ***sincrono*** ha una delle linee pilotata da un ***segnale di clock*** che stabilisce la cadenza di tutte le operazioni

>[!caution] Asincroni
>Un `BUS` ***asincrono*** non è dotato di un *clock* ma sono le ***parti*** che comunicano su di esso a doversi ***esplicitamente sincronizzare***

- Esempi di comunicazione [[RAM#Esempio RAM Asincrona|asincrona]] e [[RAM#Esempio RAM Sincrona|sincrona]]

>[!fail] Difetto `BUS` sincroni

I `BUS` devono poter operare con ***dispositivi veloci*** e ***dispositivi lenti***
- Esso dovrà *adattarsi* per forza a quelli ***più lenti***
- I dispositivi veloci ***non possono essere sfruttati*** a pieno

>[!done] Pro `BUS` sincroni

***Complessità di progettazione*** altamente inferiore

### Arbitraggio del BUS
>[!question] Problema: Più dispositivi master vogliono usare uno stesso `BUS`

Questa è una situazione ***elettricamente non possibile***
- È necessaria una ***sequenzalizzazione*** delle *richieste*

>[!info] Arbitraggio
>Per ***arbitraggio del `BUS`*** si intende una politica di gestione del `BUS` che anche a seguito di *richieste multiple* assegna il `BUS` a ***un dispositivo per volta***

Ci sono 2 tipi di ***arbitraggio***:
- ***Centralizzato*** 
- ***Distribuito***
#### Arbitraggio Centralizzato
>*Il metodo di arbitraggio centralizzato più noto è detto* ***daisy chaining***

![[Daisy_Chain.png]]

>[!abstract] *Daisy chaining*:
1. Una linea di ***Grant***, in *output* dal ***chip arbitro***, è collegate in serie a tutti i dispositivi che possono richiedere di ***diventare master***
2. Una linea ***richiesta***, comune a tutti i dispositivi, è collegata in *input* al ***chip arbitro***
3. Quando un dispositivo necessita di ***diventare master***:
	-  Manda un segnale sulla ***linea di richiesta***
		-  Questo può avvenire anche per ***più dispositivi alla volta***
	-  L'arbitro a seguito della richiesta ***attiva la linea di grant*** senza sapere da chi è arrivata
4. Il dispositivo **più vicino** all'*arbitro* controlla per sapere se è stato ***lui il richiedente***
	-  In caso affermativo ***non propaga il segnale***
	-  In caso negativo il segnale viene ***propagato al secondo dispositivo*** e via così

>[!important] Priorità

La ***distanza dall'arbitro*** stabilisce le priorità dei dispositivi sul `BUS`
- Normalmente le *periferiche* hanno ***priorità maggiore*** della `CPU`

Il ***daisy chaining*** può essere implementato a ***più livelli***:
- In questo caso i livelli più ***bassi*** hanno ***precedenza*** su quelli più ***alti***

#### Arbitraggio Decentralizzato
>*Un esempio di **arbitraggio decentralizzato** è quello in cui vengono utilizzate 16 linee di richiesta del `BUS`*

Ogni dispositivo è collegato a tutte $16$ le linee
- È sempre in grado di valutare *autonomamente* se è lui il richiedente con la ***priorità più eleveta***

>[!warning] Non occorre alcun arbitro ma deve essere presente un *protocollo* che ogni dispositivo conosce

![[Pasted image 20240425173719.png]]
>*Variante decentralizzata del daisy chaining*

- Quando il dispositivo prende il controllo del `BUS`, nega il proprio output di ***grant*** e attiva la linea ***busy***

## PCI
---
### Primi BUS
>[!info] PC Bus IBM
>Primo `BUS` per ***PC*** introdotto da *IBM* per sistemi basati su Intel $8088$ 
>Questo `BUS` *sincrono* aveva:
>- $8$ linee *dati*
>- $20$ linee *indirizzo*
>- $2$ linee per *lettura/scrittura* in memoria
>- $2$ linee per *lettura/scrittura* di $I/O$
>- Alcune linee per interrupt e #add_links DMA
>
>In totale $63$ linee

>[!abstract] BUS *ISA*
>***I***ndustry ***S***tandard ***A***rchitecture
>Quando *IBM* decise di *restrutturare* il `BUS` ormai obsoleto altre industrie reagirono e adottarono uno ***standard proprio***
>Il `BUS` *ISA* è sostanzialmente una variazione del `PC/AT` una variante del primo `BUS PC/IBM`

>[!warning] Problema: La larghezza di banda del `BUS ISA` ($8.33MHz$) ***non era sufficiente*** per molte applicazioni e periferiche

### BUS PCI
>[!info] ***P***eripheral ***C***omponent ***I***nterconnect
>Introdotto da *Intel* nel $1990$ per far fronte alla sempre crescente necessità di ***band width***
>Il `BUS` originale è un `BUS` sincrono con $32$ linee dati e opera a $33MHz$, consentendo una ***band width*** di $133 MB/sec$
>Le versioni successive hanno ulteriormente ampliato la banda massima ($528MB/sec$)
>- Portando a $64$ le linee dati e a $66MHz$ la frequenza di funzionamento

- Gli slot `PCI` hanno forme *leggermente diverse* a seconda della tensione di funzionamento e del `BUS` dati ($32$ o $64$ `BIT`)
![[PCI_BUS.png]]

Sul `PCI` per limitare il numero di *contatti* le linee dati e indirizzi sono ***comuni*** 
- Indirizzi e dati devono occupare fisicamente le linee in *istanti diversi* ***sincronizzati dal clock***



L'[[#Arbitraggio del BUS|arbitro]] (***arbitraggio centralizzato***), spesso implementato in uno dei chip "*bridge*", decide quale dei dispositivi richiedenti ha priorità maggiore

![[PCI arbiter.png]]

## USB
---
>[!info] ***U***niversal ***S***erial ***B***us
>L'`USB` nasce nella metà degli anni $'90$ dalla collaborazione di diverse aziende tra cui:
>- DEC, IBM, Intel, Microsoft
>
>Per risolvere un problema del collegamento al `PC` di periferiche "*lente*"

>[!example] Obbiettivi

- Non obbligare l'utente a smontare il `PC` per impostare dei "*jumper*"
- Un solo tipo di cavo ***poco costoso*** e ***sufficientemente lungo***
- ***Alimentare dispositivi***, o almeno la maggior parte di essi, *attraverso il cavo*
- Collegare molti dispositivi (fino a $127$) allo stesso `PC`
- Supportare dispositivi che richiedono di operare in ***tempo reale***
- Poter ***collegare/scollegare*** a `PC` accesso le periferiche *senza riavviare*

>[!done] Gli obbiettivi furono centrati e `USB` oggi è uno degli standard più diffusi

### Caratteristiche
| Versione  | Band Width  |                  Linee nel Cavo                   |
|:---------:|:-----------:|:-------------------------------------------------:|
|   $1.1$   | $1.5Mb / s$ | $2$ linee *dati* $+$ $2$ linee di *alimentazione* |
|   $2.0$   | $60Mb / s$  | $2$ linee *dati* $+$ $2$ linee di *alimentazione* |
|   $3.0$   | $600Mb / s$ | $7$ linee *dati* $+$ $2$ linee di *alimentazione* |
|   $3.2$   | $2.4Gb / s$ | $7$ linee *dati* $+$ $2$ linee di *alimentazione* |
| `USB` $4$ | $4.8Gb / s$ |                       $24$                        |
### Protocollo di Comunicazione
Il protocollo supporta $4$ ***modalità di comunicazione***:

>[!abstract] Control
>Configurazione e controllo

>[!abstract] Isochronous
>Fornisce *ampiezza di banda continuativa*

>[!abstract] Bulk
>Trasferimento di *grosse quantità di dati*

>[!abstract] Interrupt
>Scambio di *pochi dati* a *bassa latenza* (***tastiera o mouse***)

### Connettori
Inizialmente i connettori erano diversi per ***lato host*** (***A***) e ***lato device*** (***B***)
![[USBports.png]]
Da `USB` $3.1$ è disponibile anche lo standard per cavi e connettori `USB-C`
- $24$ pin simmetrici

### FireWire e Thunderbolt
>[!info] FireWire
>***FireWire*** era un `BUS` di comunicazione seriale per dispositivi ad alte prestazioni
>Analogo a `USB` ma *più performante e costoso*

Presto abbandonato a favore di `USB 3` e ***Thunderbolt***

>[!info] Thunderbolt
>Tecnologia sviluppata da *intel* in collaborazione con *Apple*, che combina i protocolli di trasferimento [[Schede Grafiche#Principali formati|Display Port]] e #add_links PciExpress in un ***unico flusso di dati***
>