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

