>[!info] Tecnica del Pipelining
>Con la tecnica del ***pipelining*** l'esecuzione di ogni istruzione viene ***suddivisa in più fasi***, chiamate ***stadi***, ognuna delle quali viene *gestita* da un ***hardware dedicato***
>>[!done] Idea
>>L'idea principale è quella di una ***catena di montaggio***, l'ideale sarebbe che la pipeline dovrebbe essere ***sempre piena***, ogni circuito non rimane mai inattivo

>[!question] [[Tipologie di Architetture#CISC|CISC]] o [[Tipologie di Architetture#RISC|RISC]] ?
>Solitamente le pipeline vengono utilizzate su macchine `RISC` poiché quest'ultime quasi tutte le istruzioni hanno lo ***stesso tempo di esecuzione*** 

![[Pipelining.png]]

Se il ciclo di clock della macchina è di $2ns$ sono necessari $10ns$ per completare l'esecuzione della prima istruzione
- ***Nessun risparmio*** rispetto all'assenza di pipelining

Una volta riempita la ***pipeline*** si completerà ***una istruzione ogni*** $2ns$

>[!warning] Problemi

>[!abstract] Dipendenza Funzionale

È necessario che le istruzioni ***non siano in conflitto***, ossia che non dipendano l'una dall'altra
- In caso contrario sarà necessario attendere il comportamento dell'istruzione precedente prima di avviare la successiva

```c
x=a+b;
y=x+c
```

>[!abstract] Salti Condizionali

Nel caso che ci sia un ***salto condizionale*** (`if` o `while`) quale istruzione ***dovrebbe iniziare a eseguire*** la pipeline?

