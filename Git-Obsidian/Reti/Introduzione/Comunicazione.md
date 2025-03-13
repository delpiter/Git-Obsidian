## Tipi di Trasferimento dei Dati
---
>[!caution] Connection Oriented

>[!abstract] Connectionless
>In un trasferimento di dati di tipo ***connectionless*** non è necessario instaurare alcuna connessione prima di effettuare il *trasferimento dei dati*.

## Fasi della Comunicazione
---
>[!abstract] Instaurazione del Circuito

Prima che i [[Segnali]] di utente possano essere trasmessi, la rete deve instaurare un circuito fra **terminale chiamante** e **terminale chiamato** (circuito *end-to-end*)

>[!tl;dr] Dialogo

I due terminali si ***scambiano informazioni*** utilizzando il circuito dedicato.

>[!caution] Disconnessione

Al termine del dialogo il circuito deve essere rilasciato al fine di poter essere usato per altre chiamate.

## Flussi di Comunicazione
---
![[CommunicationFlow.png]]

>[!Regola Generale]
>Il singolo ***flusso informativo*** è identificato da:
>- [[Protocollo IP|IP]] **sorgente** e **destinatario**.
>- [[Livello di Trasporto#Numero di Porta|Numero di Porta]] **sorgente** e **destinatario**.
