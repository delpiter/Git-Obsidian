## Tipi di Comunicazione
---
### Connection Oriented
>[!caution] Concetto
>Una modalità di fornire un servizio si dice ***connection oriented*** quando si stabilisce una **connessione**.
>Una *connessione* è una ***associazione logica*** fra due o più sistemi al fine di trasferire informazioni.

#### Fasi della Comunicazione
>[!abstract] Instaurazione della Connessione
>Fatto tramite lo scambio di opportune ***informazioni iniziali***

Prima che i [[Segnali]] di utente possano essere trasmessi, la rete deve instaurare un circuito fra **terminale chiamante** e **terminale chiamato** (circuito *end-to-end*)

>[!tl;dr] Dialogo
>Trasferimento dei *dati* veri e propri

I due terminali si ***scambiano informazioni*** utilizzando il circuito dedicato.

>[!caution] Disconnessione

Al termine del dialogo il circuito deve essere rilasciato al fine di poter essere usato per altre chiamate.

### Connectionless
>[!abstract] Concetto
>In un trasferimento di dati di tipo ***connectionless*** non è necessario instaurare alcuna connessione prima di effettuare il *trasferimento dei dati*.
>- Per ogni *accesso al servizio* vengono fornite **tutte le informazioni necessarie** per il trasferimento dei dati.
>
>>[!done] Ogni unità di dati viene trasferita in modo **indipendente** dalle altre.

### Modalità di Dialogo
> 3 Modalità di dialogo:

>[!done] Confermato
>Il dialogo ***confermato*** prevede una esplicita conferma da parte del destinatario
>- [[#Connection Oriented]]

>[!missing] Non Confermato
>Il dialogo ***non confermato*** non prevede alcuna conferma.
>- [[#Connectionless]]

>[!question] Parzialmente Confermato
>La *richiesta* viene **confermata** dal service-provider.

![[DialogMode.png|300]]
## Flussi di Comunicazione
---
![[CommunicationFlow.png]]

>[!Regola Generale]
>Il singolo ***flusso informativo*** è identificato da:
>- [[Protocollo IP|IP]] **sorgente** e **destinatario**.
>- [[Livello di Trasporto#Numero di Porta|Numero di Porta]] **sorgente** e **destinatario**.
