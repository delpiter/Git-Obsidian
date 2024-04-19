## RAM Statica
---
>[!info] `SRAM`
>Le `SRAM` sono realizzate con circuiti simili a [[Circuiti Sequenziali#Flip-Flop|flip-flop]] di tipo `D`
>Tali memorie sono *molto veloci*, ***alcuni nanosecondi*** per *lettura e scrittura*
>- Tali memorie sono anche ***piuttosto costose***
>
>Questo tipo di memoria viene tipicamente utilizzato per realizzare ***registri*** e ***cache***, entrambe interni alla `CPU`

![[Screenshot 2024-04-18 113408.png]]
>*Registro a $8$ `BIT`, realizzato con $8$ Flip-Flop D*

- Gli $8$ *flip-flop* hanno gli ***input clock*** collegati fra di loro e sono pilotati da una porta `NOT`
	- In questo circuito la memoria è *attivata* sul ***fronte di discesa***
- Per la scrittura è sufficiente rendere i dati stabili sugli *input* $I_{n}$, e inviare un ***impulso*** su `CK`
- Il `BYTE` memorizzato è ***sempre disponibile*** sui pin $O_{n}$

### Realizzazione di un Chip `SRAM`
>*La figura che segue, mostra lo schema di una `SRAM` $4\times 3$ realizzata con $12$ flip-flop D*

![[Screenshot 2024-04-18 115019.png]]
- $I_{0},I_{1},I_{2}$ sono gli *input dati*, necessari per la ***scrittura*** di un dato in *memoria*
- $O_{0},O_{1},O_{2}$ sono gli *output dati*, nei quali ***verranno posti dalla memoria*** le *parole* che devono essere messe in *output*
- $A_{0},A_{1}$ sono i due input per la *selezione dell'indirizzo* della ***parola di interesse***

>[!tldr] Addres Decoder
>Nella parte centrale a sinistra si può trovare un ***decoder*** che decifra l'indirizzo $A_{0},A_{1}$ e attiva di conseguenza la linea ***corrispondente all'indirizzo***

>[!info] `CS` `RD` `OE`
>>[!tip] *C*hip *S*elect
>>Il ***chip select*** abilita il chip per scritture o letture
>
>>[!tldr] *R*ea*D*
>>L'*input* ***read*** indica se il circuito verrà usato per *scrivere* ($1$) o per *leggere* ($0$)
>
>>[!abstract] *O*utput *E*nable
>>Indica al ***chip*** se deve o meno mandare in *output* i *valori letti*

### Read
In fase di ***lettura*** `CS`, `RD` e `OE` sono "*alti*", pertanto:
- Il ***clock*** dei *flip-flop* non viene mai *attivato*
- Gli *output* $Q$ della parola selezionata "*passano*" attraverso le porte `AND` selezionate dal decodificatore di indirizzi per giungere agli `OR` a 4 *input*

Come ultimo stadio, le uscite degli `OR` sono collegate a [[Definizioni_Architettura#Tri-State Buffer|tri-state buffer]]
- Nel circuito appare come ***simbolo triangolare***
- Agiscono come *interruttori elettronici* capaci di ***collegare/scollegare elettricamente*** due parti di un circuito

L'`AND` a tre *input* (`CS`$\cdot$`RD`$\cdot$`OE`) abilita i *buffer tri-state* di uscita rendendo disponibile la parola selezionata su $O_{1},O_{2},O_{3}$

>[!question] Perché usare un *buffer tri-state* al posto di un semplice `AND`?

Il bus di *dati* è unico per *input* e *output* 
- È necessario quindi, quando non serve, non mandare nulla in output per evitare interferenze
- A differenza della porta `AND` il *buffer tri-state* toglie *interamente* la *corrente*
### Write
In fase di ***scrittura*** `CS` ha un valore "*alto*", mentre `RD` e `OE` hanno valore "*basso*"
- I dati devono essere disponibili su $I_{0},I_{1},I_{2}$
- L'output della porta `CS`$\cdot$`!RD` è ora "*alto*" e il ***clock*** dei *flip-flop* della parola selezionata viene attivato permettendo la scrittura nella `RAM`

## RAM Dinamica
---
>[!info] *D*ynamic *RAM*
>Le `DRAM` non sono realizzate con *flip-flop* ma con ***array di celle*** ognuna costituita da un ***transistor*** più un ***condensatore***

![[Pasted image 20240418184121.png]]

>[!tldr] Condensatore
>Il ***condensatore*** è un componente in grado di mantenere per un *piccolo periodo* la ***carica elettrica*** accumulata (*memoria*)

È necessario prevedere un ***circuito di rinfresco*** delle cariche
- Ogni pochi millisecondi tale circuito "*ricarica*" le celle attive consentendo loro di ***mantenere lo stato logico***


### Differenza `DRAM` e `SRAM`
Rispetto alle `SRAM` le `DRAM` sono più ***economiche e dense***
- Circa un *transistor* contro 6 per ogni `BIT`

Sono anche ***significativamente più lente*** 

### DRAM Asincrone
>[!info] *A*sync *DRAM*
>Le prime `DRAM` erano ***asincrone***, la comunicazione con la [[La CPU|CPU]] non è sincronizzata da un ***segnale di clock***
>Sono necessarie ***linee di sincronizzazione addizionali*** perché le parti possano *scambiare le informazioni*

#### Esempio
>*Esempio di lettura da parte della `CPU` di dati da memoria asincrona sul `BUS` che collega `CPU` e memoria*

![[Pasted image 20240419110406.png]]
>[!abstract] "*Legenda*"
>- Le linee "*doppie*", come *ADDRESS* e *DATA*, sono dei `BUS`, formati da *tanti fili elettrici* quanti sono i `BIT` che trasporta.
>	- L'*incrocio* fra queste linee indica che è stata effettuata una ***scrittura***
>
>- Le linee "*singole*", Come *MSYN* e *SSYN*, sono dei semplici ***dati di controllo***, formati da *un singolo filo elettrico* che assume o $0$ o $1$
>- Una barra sopra a uno dei `BUS` di controllo indica che quel `BUS` è **attivo** a *livello basso*
>- Il cambio di stato da $0$ a $1$ o viceversa è rappresentato da una *linea obliqua* per dire che il passaggio ***non è istantaneo***

>[!attention] Funzionamento

- La `CPU` rende disponibile sul `BUS` indirizzi (*ADDRESS*) l'***indirizzo della cella di memoria*** che vuole *leggere*
- La `CPU` attiva `MREQ` (***M***emory ***Req***uest), `RD` (*Accesso alla memoria* in lettura) e infine `MSYN` attivato con un piccolo delay per ***assicurarsi la stabilità elettrica degli input***
	- (***M***aster ***Syn***cronization) un segnale di *sincronizzazione* `CPU`
- Quando la memoria vede `MSYN` esegue il lavoro nel minor tempo possibile, e non appena è pronta rende disponibile il valore sul `BUS` *dati* (*DATA*) e attiva `SSYN` 
	- (***S***lave ***Syn***cronization)un segnale di *sincronizzazione memoria*
- Quando la `CPU` vede `SSYN` attivo, legge i dati dal `BUS` *dati* e disattiva `MREQ`, `RD` e `MSYN`
	- La memoria a sua volta disattiva `SSYN`

>[!done] HandShake
>La sequenza di ***eventi interlacciati*** che caratterizza lo scambio di dati *asincrono* prende il nome di ***handshake***

