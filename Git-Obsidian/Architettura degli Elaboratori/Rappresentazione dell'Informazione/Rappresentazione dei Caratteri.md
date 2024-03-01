>[!info] Intro
> Ogni calcolatore dispone di un set di caratteri da utilizzare
- All'interno del calcolatore i caratteri sono codificati sotto forma di numeri

Per associare a ciascun numero un carattere specifico è necessario introdurre una mappatura
- Questa mappatura dei caratteri in numeri è detta ***codice di caratteri***
- Per potere comunicare è essenziale che tutti i calcolatori utilizzino la stessa mappatura
## ASCII
---
>[!info] American Standard Code for Information Interchange
> L'***ASCII*** è una delle mappature standard per la comunicazione elettronica

Ogni carattere `ASCII` utilizza 7 `BIT`
- Sono quindi possibili $128$ configurazioni

>[!tip] CheckSum

Dato che  i dati vengono trasmessi in `BYTE` l'ottavo `BIT` viene utilizzato per verificare la correttezza del dato inviato
- Questo ottavo `BIT` viene chiamato **check `BIT`** o [[Definizioni_Architettura#Parity Bit|parity `BIT`]]
- Il formato `ASCII` non viene ormai più utilizzato come protocollo di trasmissione
	- Ne consegue il fatto che l'ottavo `BIT` viene normalmente utilizzato per codificare caratteri *non-standard*
### Caratteri di Controllo
>[!info] 
>I caratteri da $0$ a $1F_{16}$ ($31_{10}$) sono **caratteri di controllo** e non vengono stampati

Molti dei caratteri di controllo servivano alla trasmissione dei dati, ma con l'evoluzione dei *protocolli di comunicazione* non vengono più utilizzati
